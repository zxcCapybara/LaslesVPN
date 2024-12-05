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
		<div class="feedback-cards">
			<Feedback></Feedback>
			<Feedback></Feedback>
			<Feedback></Feedback>
			<Feedback></Feedback>
		</div>
		<div class="feedback-cards-btn">
			<div class="left-btn">
				<div class="active"></div>
				<div></div>
				<div></div>
				<div></div>
			</div>
			<div class="right-btn">
				<button class="left">
					<img
						src="../src/assets/img/Button/nonact/eva_arrow-back-fill.png"
						alt=""
					/>
				</button>
				<button class="right">
					<img
						src="../src/assets/img/Button/act/eva_arrow-back-fill.png"
						alt=""
					/>
				</button>
			</div>
		</div>
	</div>

	<footer>
		<div class="subscribe">
			<div class="subscribe-text">
				<h5>Subscribe Now for Get Special Features!</h5>
				<p>Let's subscribe with us and find the fun.</p>
			</div>
			<Button2><slot>Subscribe Now</slot></Button2>
		</div>
		<div class="company">
			<a href="#" class="logo">
				<img src="./assets/Icon/logo.png" alt="logo" />
				<h4>Lasles<strong>VPN</strong></h4>
			</a>
			<p>
				<strong>LaslesVPN</strong> is a private virtual network that has unique
				features and has high security.
			</p>
			<div class="social">
				<a href="#"
					><img src="./assets/img/Socmed/Facebook.png" alt="facebook"
				/></a>
				<a href="#">
					<img src="./assets/img/Socmed/Twitter.png" alt="Twitter" />
				</a>
				<a href="#">
					<img src="./assets/img/Socmed/Instagram.png" alt="Instagram" />
				</a>
			</div>
			<p>©2020LaslesVPN</p>
		</div>
		<div class="product">
			<h4>Product</h4>
			<a href="#">
				<p>Download</p> </a
			><a href="#">
				<p>Pricing</p> </a
			><a href="#">
				<p>Locations</p> </a
			><a href="#">
				<p>Server</p> </a
			><a href="#">
				<p>Countries</p> </a
			><a href="#">
				<p>Blog</p>
			</a>
		</div>
		<div class="engage">
			<h4>Engage</h4>
			<a href="#">
				<p>LaslesVPN ?</p> </a
			><a href="#">
				<p>FAQ</p> </a
			><a href="#">
				<p>Tutorials</p> </a
			><a href="#">
				<p>About Us</p> </a
			><a href="#">
				<p>Privacy Policy</p> </a
			><a href="#">
				<p>Terms of Service</p>
			</a>
		</div>
		<div class="money">
			<h4>Earn Money</h4>
			<a href="#">
				<p>Affiliate</p> </a
			><a href="#">
				<p>Become Partner</p>
			</a>
		</div>
	</footer>
</template>

<script setup>
import Button2 from './components/Button2.vue'
import Feedback from './components/Feedback.vue'
import Header from './components/Header.vue'
import NamedSlots from './components/NamedSlots.vue'
</script>

<style lang="scss" scoped>
@import './assets/styles/app.scss';
</style>
