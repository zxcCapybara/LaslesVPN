<template>
	<Card>
		<template #free>
			<h6>Free Plan</h6>
			<ul>
				<li>
					<img src="../assets/img/check.png" alt="check" /><span
						>Unlimited Bandwitch</span
					>
				</li>
				<li>
					<img src="../assets/img/check.png" alt="check" /><span
						>Encrypted Connection</span
					>
				</li>
				<li>
					<img src="../assets/img/check.png" alt="check" /><span
						>No Traffic Logs</span
					>
				</li>
				<li>
					<img src="../assets/img/check.png" alt="check" /><span
						>Works on All Devices</span
					>
				</li>
			</ul>
		</template>
		<template #footer>
			<h5>Free</h5>
		</template>
	</Card>
	<Card>
		<template #standard>
			<h6>Standard Plan</h6>
			<ul>
				<li>
					<img src="../assets/img/check.png" alt="check" /><span
						>Unlimited Bandwitch</span
					>
				</li>
				<li>
					<img src="../assets/img/check.png" alt="check" /><span
						>Encrypted Connection</span
					>
				</li>
				<li>
					<img src="../assets/img/check.png" alt="check" /><span
						>No Traffic Logs</span
					>
				</li>
				<li>
					<img src="../assets/img/check.png" alt="check" /><span
						>Works on All Devices</span
					>
				</li>
				<li>
					<img src="../assets/img/check.png" alt="check" /><span
						>Connect Anyware</span
					>
				</li>
			</ul>
		</template>
		<template #footer>
			<p><strong>$9 </strong>/ mo</p>
		</template>
	</Card>
	<Card>
		<template #premium>
			<h6>Premium Plan</h6>
			<ul>
				<li>
					<img src="../assets/img/check.png" alt="check" /><span
						>Unlimited Bandwitch</span
					>
				</li>
				<li>
					<img src="../assets/img/check.png" alt="check" /><span
						>Encrypted Connection</span
					>
				</li>
				<li>
					<img src="../assets/img/check.png" alt="check" /><span
						>No Traffic Logs</span
					>
				</li>
				<li>
					<img src="../assets/img/check.png" alt="check" /><span
						>Works on All Devices</span
					>
				</li>
				<li>
					<img src="../assets/img/check.png" alt="check" /><span
						>Connect Anyware</span
					>
				</li>
				<li>
					<img src="../assets/img/check.png" alt="check" /><span
						>Get New Features</span
					>
				</li>
			</ul>
		</template>
		<template #footer>
			<p><strong>$12 </strong>/ mo</p>
			
		</template>
	</Card>
</template>
<script setup>
 import Card from '../components/Card.vue'
</script>
<style lang="scss" scoped>
@import url(../assets/styles/card.scss);
	
</style>