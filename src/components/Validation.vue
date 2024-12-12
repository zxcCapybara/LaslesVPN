<template>
	<main>
		<div class="container">
			<div class="field">
				<label class="label">Имя</label>
				<div class="control">
					<input
						v-model="form.name"
						@focus="v.$reset()"
						:class="{ 'is-danger': !!validate({ prop: 'name' }) }"
						class="input"
						type="text"
					/>
					<p v-if="!!validate({ prop: 'name' })">
						{{ validate({ prop: 'name' }) }}
					</p>
				</div>
			</div>

			<div class="field">
				<label class="label">Почта</label>
				<div class="control">
					<input
						v-model="form.email"
						@focus="v.$reset()"
						:class="{ 'is-danger': !!validate({ prop: 'email' }) }"
						class="input"
						type="text"
					/>
					<p v-if="!!validate({ prop: 'email' })">
						{{ validate({ prop: 'email' }) }}
					</p>
				</div>
			</div>

			<div class="field">
				<label class="label">Номер телефона</label>
				<div class="control">
					<input
						v-model="form.phone"
						@focus="v.$reset()"
						:class="{ 'is-danger': !!validate({ prop: 'phone' }) }"
						v-maska
						:data-maska="'+7 (###) - ### - ## - ##'"
						class="input"
						type="tel"
					/>
					<p v-if="!!validate({ prop: 'phone' })">
						{{ validate({ prop: 'phone' }) }}
					</p>
				</div>
			</div>

			<div class="field">
				<label class="label">Сообщение</label>
				<div class="control">
					<textarea
						v-model="form.textarea"
						@focus="v.$reset()"
						:class="{ 'is-danger': !!validate({ prop: 'textarea' }) }"
						class="textarea"
						type="text"
					/>
					<p v-if="!!validate({ prop: 'textarea' })">
						{{ validate({ prop: 'textarea' }) }}
					</p>
				</div>
			</div>

			<div class="field">
				<label class="label">Пароль</label>
				<div class="control">
					<input
						v-model="form.password"
						@focus="v.$reset()"
						:class="{ 'is-danger': !!validate({ prop: 'password' }) }"
						class="input"
						type="password"
					/>
					<p v-if="!!validate({ prop: 'password' })">
						{{ validate({ prop: 'password' }) }}
					</p>
				</div>
			</div>

			<div class="field">
				<label class="label">Повторите пароль</label>
				<div class="control">
					<input
						v-model="form.currentPassword"
						@focus="v.$reset()"
						:class="{ 'is-danger': !!validate({ prop: 'currentPassword' }) }"
						class="input"
						type="password"
					/>
					<p v-if="!!validate({ prop: 'currentPassword' })">
						{{ validate({ prop: 'currentPassword' }) }}
					</p>
				</div>
			</div>

			<div class="field">
				<label
					class="label"
					:class="{ 'is-danger-label': !!validate({ prop: 'checkbox' }) }"
				>
					<div class="control usn">
						<input
							v-model="form.checkbox"
							@focus="v.$reset()"
							type="checkbox"
						/>
						Я соглашаюсь с
						<a href="#">правилами сообщества </a>
					</div>
				</label>
			</div>
			<div class="control">
				<button
					:disabled="form.pending"
					:class="{ 'is-loading': form.pending }"
					class="btn button"
					@click="onSubmit"
				>
					<span>Отправить</span>
					
				</button>
			</div>
			<div class="close"><slot name="close"></slot></div>
		</div>
	</main>
</template>
<script>
import {
	email,
	maxLength,
	minLength,
	required,
	requiredPhone,
	sameAs,
} from '../assets/utils/i18n-validators.js'

import useValidate from '@vuelidate/core'
import { vMaska } from 'maska/vue'
import { computed, reactive } from 'vue'

export default {
	setup() {
		// data

		const form = reactive({
			name: null,
			email: null,
			phone: null,
			textarea: null,
			password: null,
			currentPassword: null,
			checkbox: null,
			pending: null,
		})

		// computed

		const rules = computed(() => ({
			name: {
				required,
			},
			email: {
				required,
				email,
			},
			phone: {
				required,
				requiredPhone: requiredPhone(24),
			},
			textarea: {
				required,
				minLength: minLength(5),
			},
			password: {
				required,
				minLength: minLength(5),
				maxLength: maxLength(25),
			},
			currentPassword: {
				required,
				minLength: minLength(5),
				maxLength: maxLength(25),
				sameAs: sameAs(form.password),
			},
			checkbox: {
				required,
				sameAs: sameAs(true),
			},
		}))

		const v = useValidate(rules, form)
		// methods
		const onSubmit = async () => {
			v.value.$touch()

			if (form.panding) return

			if (await v.value.$validate()) {
				form.pending = true

				try {
					const payload = {
						name: form.name,
						email: form.email,
						phone: form.phone,
						textarea: form.textarea,
						password: form.password,
						currentPassword: form.currentPassword,
						checkbox: form.checkbox,
					}

					setTimeout(() => {
						console.log(payload)
						console.log('Запрос отправлен')

						resetForm()
					}, 2500)
				} catch (e) {
					console.log(e)
				}
			}
		}

		const validate = ({ prop }) => {
			const error = v.value.$errors.find(el => el.$property === prop)
			return error && error.$message
		}

		const resetForm = () => {
			Object.keys(form).forEach(key => {
				form[key] = null
			})
			v.value.$reset()
		}

		return {
			v,
			form,
			onSubmit,
			validate,
		}
	},

	directives: {
		maska: vMaska,
	},
}
</script>

<style lang="scss" scoped>
.close {
	position: absolute;
	top: 40px;
	right: 40px;
}

main {
	color: rgb(255, 255, 255);
	height: 100vh;
	display: flex;
	flex-direction: column;
	justify-content: center;
	align-items: center;
	width: 100%;
}

.container {
	width: 1400px;
	height: 950px;
	background-color: rgb(175, 175, 175);
	border-radius: 40px;
	padding: 40px;
	display: flex;
	flex-direction: column;
	align-items: center;
	justify-content: center;
	gap: 25px;
	position: relative;
}

.field {
	display: flex;
	flex-direction: column;
	align-items: center;
	width: 80%;
}

.control {
	width: 100%;
	display: flex;
	justify-content: center;
	flex-direction: column;
	align-items: center;

	p {
		text-align: center;
		color: rgb(180, 4, 4);
	}
}

.input,
.textarea {
	border: none;
	outline: none;
	border-radius: 5px;
	height: 35px;
	width: 20vw;
	padding: 5px;
	resize: none;
	// background-color: rgb(255, 255, 255);
}

.textarea {
	height: 45px;
}

.usn {
	user-select: none;
	display: block;
}

.btn {
	border: none;
	// background-color: rgb(214, 214, 214);
	cursor: pointer;
	user-select: none;
	border-radius: 10px;
	width: 40%;
	height: 40px;

	&:hover {
		background-color: #f53838;
		border: none;
		color: #fff;
		transition: 0.3s;
	}

	&:active {
		transform: scale(1.1);
	}

	&:disabled {
		cursor: not-allowed;
		background-color: rgb(143, 143, 143);
		transform: scale(1);
		color: rgb(40, 39, 39);
	}
}

.is-loading {
	cursor: wait !important;
	background-color: rgb(143, 143, 143);

	&:hover {
		background-color: rgb(143, 143, 143);
	}

	&:active {
		transform: none;
	}

	&::after {
		content: 'Loading...';
		color: rgb(40, 39, 39);
	}

	span {
		display: none;
	}
}

.is-danger {
	background-color: #f53838;
}

.is-danger-label {
	color: rgb(182, 2, 2);
}

.label {
	margin-bottom: 5px;
}
</style>
