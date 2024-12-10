<script setup>
import { ref } from 'vue'
import { Carousel, Pagination, Slide } from 'vue3-carousel'
import 'vue3-carousel/dist/carousel.css'
import Feedback from './Feedback.vue'

const carouselRef = ref()
const currentSlide = ref(0)

const next = () => carouselRef.value.next()
const prev = () => carouselRef.value.prev()

let cards = [
	{
		id: 1,
		url: '../src/assets/img/user1.png',
		name: 'Viezh Robert',
		country: 'Warsaw, Poland',
		rating: '4.5',
		text: '“Wow... I am very happy to use this VPN, it turned out to be more than my expectations and so far there have been no problems. LaslesVPN always the best”',
	},
	{
		id: 2,
		url: '../src/assets/img/user2.png',
		name: 'Yessica Christy',
		country: 'Shanxi, China',
		rating: '4',
		text: '“I like it because I like to travel far and still can connect with high speed.”',
	},
	{
		id: 3,
		url: '../src/assets/img/user3.png',
		name: 'Kim Young Jou',
		country: 'Seoul, South Korea',
		rating: '3.5',
		text: '“This is very unusual for my business that currently requires a virtual private network that has high security.”',
	},
	{
		id: 4,
		url: '../src/assets/img/user1.png',
		name: 'Viezh Robert',
		country: 'Warsaw, Poland',
		rating: '4.5',
		text: '“Wow... I am very happy to use this VPN, it turned out to be more than my expectations and so far there have been no problems. LaslesVPN always the best”',
	},
	{
		id: 5,
		url: '../src/assets/img/user2.png',
		name: 'Yessica Christy',
		country: 'Shanxi, China',
		rating: '4',
		text: '“I like it because I like to travel far and still can connect with high speed.”',
	},
	{
		id: 6,
		url: '../src/assets/img/user3.png',
		name: 'Kim Young Jou',
		country: 'Seoul, South Korea',
		rating: '3.5',
		text: '“This is very unusual for my business that currently requires a virtual private network that has high security.”',
	},
]
</script>

<template>
	<Carousel
		:wrapAround="true"
		:itemsToShow="3"
		ref="carouselRef"
		v-model="currentSlide"
		
	>
		<Slide v-for="card in cards" :key="card">
			<Feedback
				:image="card.url"
				:name="card.name"
				:country="card.country"
				:rating="card.rating"
				:text="card.text"
			
			
			></Feedback>
		</Slide>

		<template class="pagination" #addons>
			<Pagination />
		</template>
	</Carousel>
	<div class="btn">
		<button class="prev" @click="prev">
			<svg
				width="30"
				height="31"
				viewBox="0 0 30 31"
				fill="none"
				xmlns="http://www.w3.org/2000/svg"
			>
				<path
					d="M23.75 14.0029H8.925L13.4625 8.55291C13.6747 8.29764 13.7768 7.96854 13.7463 7.638C13.7158 7.30747 13.5553 7.00258 13.3 6.79041C13.0447 6.57823 12.7156 6.47616 12.3851 6.50663C12.0546 6.53711 11.7497 6.69764 11.5375 6.95291L5.2875 14.4529C5.24545 14.5126 5.20785 14.5752 5.175 14.6404C5.175 14.7029 5.175 14.7404 5.0875 14.8029C5.03084 14.9462 5.00118 15.0988 5 15.2529C5.00118 15.407 5.03084 15.5596 5.0875 15.7029C5.0875 15.7654 5.0875 15.8029 5.175 15.8654C5.20785 15.9306 5.24545 15.9933 5.2875 16.0529L11.5375 23.5529C11.655 23.694 11.8022 23.8075 11.9686 23.8853C12.1349 23.963 12.3164 24.0032 12.5 24.0029C12.7921 24.0035 13.0751 23.9018 13.3 23.7154C13.4266 23.6105 13.5312 23.4816 13.6079 23.3362C13.6846 23.1907 13.7318 23.0316 13.7469 22.8679C13.762 22.7042 13.7447 22.5391 13.6959 22.3821C13.6471 22.2251 13.5678 22.0792 13.4625 21.9529L8.925 16.5029H23.75C24.0815 16.5029 24.3995 16.3712 24.6339 16.1368C24.8683 15.9024 25 15.5844 25 15.2529C25 14.9214 24.8683 14.6034 24.6339 14.369C24.3995 14.1346 24.0815 14.0029 23.75 14.0029Z"
					fill="#F53838"
				/>
			</svg>
		</button>
		<!-- <input type="number" min="0" max="9" v-model="currentSlide" /> -->
		<button class="next" @click="next">
			<svg
				width="30"
				height="31"
				viewBox="0 0 30 31"
				fill="none"
				xmlns="http://www.w3.org/2000/svg"
			>
				<path
					d="M6.25 14.0029H21.075L16.5375 8.55291C16.3253 8.29764 16.2232 7.96854 16.2537 7.638C16.2842 7.30747 16.4447 7.00258 16.7 6.79041C16.9553 6.57823 17.2844 6.47616 17.6149 6.50663C17.9454 6.53711 18.2503 6.69764 18.4625 6.95291L24.7125 14.4529C24.7545 14.5126 24.7922 14.5752 24.825 14.6404C24.825 14.7029 24.825 14.7404 24.9125 14.8029C24.9692 14.9462 24.9988 15.0988 25 15.2529C24.9988 15.407 24.9692 15.5596 24.9125 15.7029C24.9125 15.7654 24.9125 15.8029 24.825 15.8654C24.7922 15.9306 24.7545 15.9933 24.7125 16.0529L18.4625 23.5529C18.345 23.694 18.1978 23.8075 18.0314 23.8853C17.8651 23.963 17.6836 24.0032 17.5 24.0029C17.2079 24.0035 16.9249 23.9018 16.7 23.7154C16.5734 23.6105 16.4688 23.4816 16.3921 23.3362C16.3154 23.1907 16.2682 23.0316 16.2531 22.8679C16.238 22.7042 16.2553 22.5391 16.3041 22.3821C16.3529 22.2251 16.4322 22.0792 16.5375 21.9529L21.075 16.5029H6.25C5.91848 16.5029 5.60054 16.3712 5.36612 16.1368C5.13169 15.9024 5 15.5844 5 15.2529C5 14.9214 5.13169 14.6034 5.36612 14.369C5.60054 14.1346 5.91848 14.0029 6.25 14.0029Z"
					fill="white"
				/>
			</svg>
		</button>
	</div>
</template>

<style lang="scss" scoped>
@import url(../assets/styles/app.scss);
@import url(../assets/styles/carousel.scss);
</style>
