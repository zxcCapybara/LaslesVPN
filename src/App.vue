<template>
	<div class="app">
		<Header></Header>
		<main>
			<div class="main-user">
				<div class="main-text">
					<h4>Want anything to be easy with LaslesVPN.</h4>
					<p>
						Provide a network for all your needs with ease and fun using
						<strong>LaslesVPN</strong>
						discover interesting features from us.
					</p>
					<Button2><slot>Get Started</slot></Button2>
				</div>
				<img src="/src/assets/img/1.png" alt="user" />
			</div>
			<div class="main-cards">
				<div class="users">
					<img src="/src/assets/Icon/user.png" alt="user" />
					<div class="users-text">
						<h3>90+</h3>
						<p>Users</p>
					</div>
				</div>
				<svg
					xmlns="http://www.w3.org/2000/svg"
					width="3"
					height="129"
					viewBox="0 0 3 129"
					fill="none"
				>
					<path
						d="M1.5 1.76257V127.336"
						stroke="#EEEFF2"
						stroke-width="2"
						stroke-linecap="round"
					/>
				</svg>
				<div class="locations">
					<img src="/src/assets/Icon/location.png" alt="location" />
					<div class="locations-text">
						<h3>30+</h3>
						<p>Locations</p>
					</div>
				</div>
				<svg
					xmlns="http://www.w3.org/2000/svg"
					width="3"
					height="129"
					viewBox="0 0 3 129"
					fill="none"
				>
					<path
						d="M1.5 1.76257V127.336"
						stroke="#EEEFF2"
						stroke-width="2"
						stroke-linecap="round"
					/>
				</svg>
				<div class="servers">
					<img src="/src/assets/Icon/Server.png" alt="servers" />
					<div class="servers-text">
						<h3>50+</h3>
						<p>servers</p>
					</div>
				</div>
			</div>
		</main>

		<div class="main-user gap-140 mb-130">
			<img class="ml-35" src="../src/assets/img/2.png" alt="user2" />
			<div class="main-text mt-20">
				<h5>We Provide Many Features You Can Use</h5>
				<p>
					You can explore the features that we provide with fun and have their
					own functions each feature.
				</p>
				<ul>
					<li>
						<img src="../src/assets/img/galka.png" alt="galka" />
						<span>Powerfull online protection.</span>
					</li>
					<li>
						<img src="../src/assets/img/galka.png" alt="galka" />
						<span>Internet without borders.</span>
					</li>
					<li>
						<img src="../src/assets/img/galka.png" alt="galka" />
						<span>Supercharged VPN.</span>
					</li>
					<li>
						<img src="../src/assets/img/galka.png" alt="galka" />
						<span>No specific time limits.</span>
					</li>
				</ul>
			</div>
		</div>
	</div>

	<div class="plan">
		<h5>Choose Your Plan</h5>
		<p>
			Let's choose the package that is best for you and explore it happily and
			cheerfully.
		</p>
		<div class="card">
			<NamedSlots></NamedSlots>
		</div>
	</div>

	<div class="network">
		<h5>Huge Global Network of Fast VPN</h5>
		<p>
			See <strong>LaslesVPN</strong> everywhere to make it easier for you when
			you move locations.
		</p>
		<img src="../src/assets/img/global.png" alt="global" />
		<div class="group">
			<img src="../src/assets/img/netflix.png" alt="netflix" />
			<img src="../src/assets/img/reddit.png" alt="reddit" />
			<img src="../src/assets/img/amazon.png" alt="amazon" />
			<img src="../src/assets/img/discord.png" alt="discord" />
			<img src="../src/assets/img/spotify.png" alt="spotify" />
		</div>
	</div>

	<div class="feedback">
		<h5>Trusted by Thousands of Happy Customer</h5>
		<p>
			These are the stories of our customers who have joined us with great
			pleasure when using this crazy feature.
		</p>
	</div>
	<div class="carousel">
		<CarouselCard></CarouselCard>
	</div>

	<div class="subscribe">
		<div class="subscribe-text">
			<h5>Subscribe Now for Get Special Features!</h5>
			<p>Let's subscribe with us and find the fun.</p>
		</div>
		<Button2><slot>Subscribe Now</slot></Button2>
	</div>
	<Footer></Footer>
</template>

<script setup>
import Button2 from './components/Button2.vue'
import CarouselCard from './components/Carousel.vue'
import Footer from './components/Footer.vue'
import Header from './components/Header.vue'
import NamedSlots from './components/NamedSlots.vue'

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

<style lang="scss" scoped>
@import './assets/styles/app.scss';
</style>
