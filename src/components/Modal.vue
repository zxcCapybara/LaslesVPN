<script setup>
defineProps(['toggleModal'])
</script>

<template>
	<div class="modal">
		<div class="modal-inner">
			<slot />
			<button class="modal-close" @click="toggleModal()">X</button>
		</div>
	</div>
</template>

<style lang="scss">
.modal {
	position: fixed;
	top: 0;
	bottom: 0;
	left: 0;
	right: 0;
	z-index: 99;
	background-color: rgba(0, 0, 0, 0.2);
	display: flex;
	align-items: center;
	justify-content: center;

	.modal-inner {
		background-color: #fff;
		width: 90vw;
		height: 95vh;
		border-radius: 10px;
		position: relative;
	}

	.modal-close {
		position: absolute;
		border: none;
		top: 40px;
		right: 40px;
		width: 40px;
		height: 40px;
		border: 1px solid #f53838;
		background-color: #fff;
		border-radius: 5px;
		&:hover {
			background-color: #f53838;
			color: #fff;
			transition: .3s;
		}
	}
}
</style>
