<template>
	<div class="feedback-card">
		<div class="feedback-card__inner">
			<div class="user-info">
				<img :src="image" alt="user" />
				<div class="user-info__inner">
					<h6>{{ name }}</h6>
					<p>{{ country }}</p>
				</div>
			</div>
			<div class="rating">
				<span>{{ rating }}</span>
				<img src="../assets/img/star.png" alt="star" />
			</div>
		</div>

		<p class="black-text">{{ text }}</p>
	</div>
</template>
<script setup>
defineProps({
	image: String,
	name: String,
	country: String,
	rating: String,
	text: String,
})
</script>
<style lang="scss" scoped>
@import url(../assets/styles/feedback.scss
);
</style>
