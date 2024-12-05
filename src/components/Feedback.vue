<template>
	<div class="feedback-card">
		<div class="feedback-card__inner">
			<div class="user-info">
			<img src="../assets/img/user1.png" alt="user" />
			<div class="user-info__inner">
				<h6>Viezh Robert</h6>
				<p>Warsaw, Poland</p>
			</div>
		</div>
		<div class="rating">
			<span>4.5</span>
			<img src="../assets/img/star.png" alt="star" />
		</div>
		</div>
	

		<p class='black-text'
			>“Wow... I am very happy to use this VPN, it turned out to be more than my
			expectations and so far there have been no problems. LaslesVPN always the
			best”.</p
		>
	</div>
</template>
<script></script>
<style lang="scss" scoped>
.feedback-card {
	width: 400px;
	height: 230px;
	border-radius: 10px;
	border: 2px solid #ddd;
	padding: 30px;
	
}

.feedback-card__inner {
	display: flex;
	justify-content: space-between;
	align-items: center;
}

.user-info {
	display: flex;
	gap: 20px;
	align-items: center;

}



.user-info__inner {
	display: flex;
	flex-direction: column;

}

.rating {
	display: flex;
	align-items: center;
	gap: 10px;
}

.black-text {
	margin-top: 20px;
	color: #0B132A;
}

</style>
