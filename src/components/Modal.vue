<script setup>
import Validation from './Validation.vue'
const props = defineProps({
	show: Boolean,
})
</script>

<template>
	<Transition name="modal">
		<div v-if="show" class="modal-mask">
			<Validation>
				<template #close>
					<button class="btnClose" @click="$emit('close')">X</button>
				</template>
			</Validation>
		</div>
	</Transition>
</template>

<style lang="scss">
.modal-mask {
	position: fixed;
	z-index: 9998;
	top: 0;
	left: 0;
	width: 100%;
	height: 100%;
	background-color: rgba(0, 0, 0, 0.5);
	display: flex;
	transition: opacity 0.3s ease;
}

.modal-enter-from {
	opacity: 0;
}

.modal-leave-to {
	opacity: 0;
}

.modal-enter-from .modal-container,
.modal-leave-to .modal-container {
	-webkit-transform: scale(1.1);
	transform: scale(1.1);
}

.btnClose {
	border: none;
	width: 40px;
	height: 40px;
	border-radius: 10px;
	&:hover {
		background-color: #f53838;
	}
}
</style>
