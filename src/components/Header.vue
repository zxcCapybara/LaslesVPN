<template>
	<nav>
		<a href='#' class="logo">
			<img src="../assets//Icon/logo.png" alt="logo" />
			<h4>Lasles<strong>VPN</strong></h4>
		</a>
		<ul class="nav-item">
			<li class="nav-item"><a href="#">About</a></li>
			<li class="nav-item"><a href="#">Features</a></li>
			<li class="nav-item"><a href="#">Pricing</a></li>
			<li class="nav-item">
				<a href="#">Testimonials</a>
			</li>
			<li class="nav-item"><a href="#">Help</a></li>
		</ul>
		<div class="nav-login">
			<h4>Sign In</h4>
			<Button1><slot>Sign Up</slot></Button1>
		</div>
	</nav>
</template>
<script setup>
import Button1 from '../components/Button1.vue'
</script>
<style lang="scss" scoped>
@import '../assets/styles/header.scss';
</style>
