<template>
	<nav>
		<a href="#" class="logo">
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
			<button @click="() => toggleModal('signIn')" class="btn">Sign In</button>

			<Button1 @click="() => toggleModal('signUp')"
				><slot>Sign Up</slot></Button1
			>
			<Modal
				v-if="modalTrigger.signIn"
				:toggleModal="() => toggleModal('signIn')"
			>
				<ValidationSignIn></ValidationSignIn>
			</Modal>
			<Modal
				v-if="modalTrigger.signUp"
				:toggleModal="() => toggleModal('signUp')"
			>
				<Validation></Validation>
			</Modal>
		</div>
	</nav>
</template>
<script setup>
import Button1 from '../components/Button1.vue'
import Modal from './Modal.vue'
import Validation from './Validation.vue'
import ValidationSignIn from './ValidationSignIn.vue'

import { ref, watch } from 'vue'

const modalTrigger = ref({
  signUp: false,
  signIn: false,
})

const toggleModal = (trigger) => {
  modalTrigger.value[trigger] = !modalTrigger.value[trigger]
}

</script>
<style lang="scss">
@import '../assets/styles/header.scss';

.no-overflow {
	overflow: hidden;
}
</style>
