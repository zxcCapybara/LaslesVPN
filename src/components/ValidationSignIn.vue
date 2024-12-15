<template>
	<main>
		<div class="container">
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
		</div>
	</main>
</template>
<script>
import {
	email,
	maxLength,
	minLength,
	required,
} from '../assets/utils/i18n-validators.js'

import useValidate from '@vuelidate/core'
import { vMaska } from 'maska/vue'
import { computed, reactive } from 'vue'

export default {
	setup() {
		// data

		const form = reactive({
			email: null,

			password: null,

			pending: null,
		})

		// computed

		const rules = computed(() => ({
			email: {
				required,
				email,
			},

			password: {
				required,
				minLength: minLength(5),
				maxLength: maxLength(25),
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
						email: form.email,
						password: form.password,
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
main {
	display: flex;
	flex-direction: column;
	justify-content: center;
	align-items: center;
	height: 100%;
}

.container {
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
}

.control {
	width: 100%;
	display: flex;
	justify-content: center;
	flex-direction: column;
	align-items: center;
	button {
		border: 1px solid #f53838;
	}

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
	border: 1px solid #f53838;
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
	width: 100%;
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
