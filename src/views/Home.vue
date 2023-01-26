<script setup>
	import { onMounted, ref } from "vue";

	var petalPlayers = [];
	const swiper = ref(null);

	function animatePetals() {
		var petals = document.querySelectorAll(".petal");

		if (!petals[0].animate) {
			var petalsContainer = document.getElementById("petals-container");
			petalsContainer.prepend(
				"Uh oh, it seems like your browser doesn't support Web Animations API yet. Have you tried this in Firefox or Chrome?"
			);
			return false;
		}

		for (var i = 0, len = petals.length; i < len; ++i) {
			var petal = petals[i];
			petal.innerHTML =
				'<div class="rotate"><img src="https://upload.wikimedia.org/wikipedia/commons/thumb/f/f1/Heart_coraz%C3%B3n.svg/1200px-Heart_coraz%C3%B3n.svg.png" class="askew"></div>';
			var scale = Math.random() * 0.8 + 0.2;

			var player = petal.animate(
				[
					{
						transform:
							"translate3d(" +
							(i / len) * 100 +
							"100vw,0,0) scale(" +
							scale +
							")",
						opacity: scale,
					},
					{
						transform:
							"translate3d(" +
							((i / len) * 100 + 10) +
							"vw,150vh,0) scale(" +
							scale +
							")",
						opacity: 1,
					},
				],
				{
					duration: Math.random() * 90000 + 3000,
					iterations: Infinity,
					delay: -(Math.random() * 5000),
				}
			);

			petalPlayers.push(player);
		}
	}

	function start() {
		swiper.value.autoplay.start();
	}

	function stop() {
		swiper.value.autoplay.stop();
	}

	function swipe() {
		swiper.value = new Swiper(".mySwiper", {
			autoplay: {
				delay: 5000,
				disableOnInteraction: true,
			},
			effect: "coverflow",
			grabCursor: true,
			centeredSlides: true,
			slidesPerView: "auto",
			coverflowEffect: {
				rotate: 50,
				stretch: 0,
				depth: 100,
				modifier: 1,
				slideShadows: true,
			},
			pagination: {
				el: ".swiper-pagination",
				clickable: true,
			},
		});
	}

	onMounted(() => {
		animatePetals();
		swipe();
	});
</script>

<template>
	<div
		class="container w-100 position-relative text-capitalized my-2 my-mdo-5 h-100 d-flex align-items-center justify-content-center"
	>
		<div id="petals-container w-100 top-0 position-absolute">
			<div class="petal"></div>
			<div class="petal"></div>
			<div class="petal"></div>
			<div class="petal"></div>
			<div class="petal"></div>
			<div class="petal"></div>
			<div class="petal"></div>
			<div class="petal"></div>
			<div class="petal"></div>
			<div class="petal"></div>
			<div class="petal"></div>
			<div class="petal"></div>
			<div class="petal"></div>
			<div class="petal"></div>
			<div class="petal"></div>
			<div class="petal"></div>
			<div class="petal"></div>
			<div class="petal"></div>
			<div class="petal"></div>
			<div class="petal"></div>
			<div class="petal"></div>
			<div class="petal"></div>
			<div class="petal"></div>
			<div class="petal"></div>
			<div class="petal"></div>
			<div class="petal"></div>
			<div class="petal"></div>
			<div class="petal"></div>
			<div class="petal"></div>
			<div class="petal"></div>
			<div class="petal"></div>
			<div class="petal"></div>
			<div class="petal"></div>
			<div class="petal"></div>
			<div class="petal"></div>
			<div class="petal"></div>
			<div class="petal"></div>
			<div class="petal"></div>
			<div class="petal"></div>
			<div class="petal"></div>
			<div class="petal"></div>
			<div class="petal"></div>
			<div class="petal"></div>
			<div class="petal"></div>
			<div class="petal"></div>
			<div class="petal"></div>
			<div class="petal"></div>
			<div class="petal"></div>
			<div class="petal"></div>
			<div class="petal"></div>
			<div class="petal"></div>
			<div class="petal"></div>
			<div class="petal"></div>
			<div class="petal"></div>
			<div class="petal"></div>
			<div class="petal"></div>
			<div class="petal"></div>
			<div class="petal"></div>
			<div class="petal"></div>
			<div class="petal"></div>
			<div class="petal"></div>
			<div class="petal"></div>
			<div class="petal"></div>
			<div class="petal"></div>
			<div class="petal"></div>
			<div class="petal"></div>
			<div class="petal"></div>
			<div class="petal"></div>
			<div class="petal"></div>
			<div class="petal"></div>
			<div class="petal"></div>
			<div class="petal"></div>
			<div class="petal"></div>
			<div class="petal"></div>
			<div class="petal"></div>
			<div class="petal"></div>
			<div class="petal"></div>
			<div class="petal"></div>
			<div class="petal"></div>
			<div class="petal"></div>
		</div>
		<div class="rounded-cs w-100" style="max-width: 700px">
			<div
				class="swiper mySwiper rounded-cs"
				@mouseleave="start()"
				@mouseenter="stop()"
			>
				<div class="swiper-wrapper">
					<div class="swiper-slide shadow rounded-cs">
						<img
							class="rounded-cs shadow-lg img-auto"
							src="/assets/img/card-1.png"
							alt=""
						/>
					</div>
					<div class="swiper-slide rounded-cs">
						<img
							class="rounded-cs shadow-lg img-auto"
							src="/assets/img/card-2.png"
							alt=""
						/>
					</div>
					<div class="swiper-slide shadow-lg rounded-cs">
						<img
							class="rounded-cs img-auto"
							src="/assets/img/card-3.png"
							alt=""
						/>
					</div>
				</div>
				<div class="swiper-pagination"></div>
			</div>
		</div>
	</div>
</template>

<style scoped>
	.swiper {
		width: 100%;
		padding-top: 20px;
		padding-bottom: 50px;
	}

	.swiper-slide {
		background-position: center;
		background-size: cover;
		width: 270px;
		/* height: 300px; */
	}

	@media (min-width: 568px) {
		.swiper {
			width: 100%;
			padding-top: 40px;
		}

		.swiper-slide {
			width: 350px;
			/* height: 300px; */
		}
	}

	.swiper-slide img {
		display: block;
		width: 100%;
	}
	.rounded-cs {
		border-radius: 25px;
	}
	div {
		font-family: "Lora", serif;
	}

	.name {
		font-family: "hydena", cursive;
		font-weight: bold;
	}

	#petals-container {
		width: 100%;
	}
	.petal {
		width: 1rem;
		height: 1rem;
		display: inline-block;
		position: absolute;
		top: -10rem;
		bottom: 0;
		z-index: 150;
	}
	.petal .rotate {
		animation: driftyRotate 1s infinite both ease-in-out;
		perspective: 1000;
	}
	.petal .askew {
		background: currentColor;
		transform: skewY(10deg);
		display: block;
		width: 2rem;
		height: 2rem;
		animation: drifty 1s infinite alternate both ease-in-out;
		perspective: 1000;
	}

	.petal {
		color: rgba(0, 0, 0, 0);
	}
	.petal:nth-of-type(7n) .askew {
		animation-delay: -0.6s;
		animation-duration: 2.25s;
	}
	.petal:nth-of-type(7n + 1) .askew {
		animation-delay: -0.879s;
		animation-duration: 3.5s;
	}
	.petal:nth-of-type(7n + 2) .askew {
		animation-delay: -0.11s;
		animation-duration: 1.95s;
	}
	.petal:nth-of-type(7n + 3) .askew {
		animation-delay: -0.246s;
		animation-duration: 0.85s;
	}
	.petal:nth-of-type(7n + 4) .askew {
		animation-delay: -0.43s;
		animation-duration: 2.5s;
	}
	.petal:nth-of-type(7n + 5) .askew {
		animation-delay: -0.56s;
		animation-duration: 1.75s;
	}
	.petal:nth-of-type(7n + 6) .askew {
		animation-delay: -0.76s;
		animation-duration: 1.5s;
	}

	.petal:nth-of-type(9n) .rotate {
		animation-duration: 2s;
	}
	.petal:nth-of-type(9n + 1) .rotate {
		animation-duration: 2.3s;
	}
	.petal:nth-of-type(9n + 2) .rotate {
		animation-duration: 1.1s;
	}
	.petal:nth-of-type(9n + 3) .rotate {
		animation-duration: 0.75s;
	}
	.petal:nth-of-type(9n + 4) .rotate {
		animation-duration: 4.3s;
	}
	.petal:nth-of-type(9n + 5) .rotate {
		animation-duration: 3.05s;
	}
	.petal:nth-of-type(9n + 6) .rotate {
		animation-duration: 2.76s;
	}
	.petal:nth-of-type(9n + 7) .rotate {
		animation-duration: 7.6s;
	}
	.petal:nth-of-type(9n + 8) .rotate {
		animation-duration: 1.78s;
	}

	@keyframes drifty {
		0% {
			transform: skewY(10deg) translate3d(-250%, 0, 0);
			display: block;
		}
		100% {
			transform: skewY(-12deg) translate3d(250%, 0, 0);
			display: block;
		}
	}
	@keyframes driftyRotate {
		0% {
			transform: rotateX(0);
			display: block;
		}
		100% {
			transform: rotateX(359deg);
			display: block;
		}
	}
</style>
