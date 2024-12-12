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
			<button class="btn">
				Sign In
			</button>
			<Button1 id="show-modal" @click="showModal = true"
				><slot>Sign Up</slot></Button1
			>
			<Teleport to="body">
				<!-- используйте модальный компонент, передайте входной параметр -->
				<modal
					:class="{ hidden: showModal }"
					:show="showModal"
					@close="showModal = false"
				>

				</modal>
			</Teleport>
		</div>
	</nav>
</template>
<script setup>
import Button1 from '../components/Button1.vue'

import { ref, watch } from 'vue'
import Modal from './Modal.vue'

const showModal = ref(false)
const activeId = ref(null)

const bodyClassList = document.body.classList

watch(
	[showModal, activeId],
	newValues => {
		const [isVisible, id] = newValues

		bodyClassList.toggle('no-overflow', isVisible || id)
	},
	{ immediate: true }
)
</script>
<style lang="scss">
@import '../assets/styles/header.scss';

.no-overflow {
	overflow: hidden;
}
</style>
