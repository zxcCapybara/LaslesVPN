<template>
	<button><slot></slot></button>
</template>
<script>

</script>
<style lang="scss" scoped>
		button {
		position: relative;
		margin-top: 30px;
		width: 250px;
		height: 60px;
		border-radius: 10px;
		background: #f53838;
		border: none;
		color: #fff;
		cursor: pointer;
		box-shadow: 0px 25px 27px rgba(245, 56, 56, 0.35);

		&:hover {
			background-color: #fff;
			color: #f53838;
			border: 1px solid #f53838;
			transition: 0.3s;
		}
	}
</style>