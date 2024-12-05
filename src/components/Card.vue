<template>
	<button class="card">
		<div class="card__inner">
			<img src="../assets/img/Illustration/Free.png" alt="free" />
			<slot name="free"></slot>
			<slot name="standard"></slot>
			<slot name="premium"></slot>
		</div>

		<div class="footer">
			<slot name='footer'></slot>
			<Button1 class="w-178"><slot>Select</slot></Button1>
		</div>
	</button>
</template>
<script setup>
import Button1 from '../components/Button1.vue'

</script>
<style lang="scss" scoped>
@import url(../assets/styles/card.scss);
</style>
