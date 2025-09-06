<img
	src="pfpmain.webp"
	alt="M_Dragonborn"
/>

<style lang="scss">
	img {
		cursor: pointer;
		width: 1600px;
		border-radius: 20px;
		animation-name: hovering;
		animation-timing-function: ease-in-out;
		animation-duration: 2.5s;
		animation-iteration-count: infinite;
		transition: 0.3s filter ease;
		&:hover {
			filter: brightness(1.3);
		}

		@media (max-width: 505px) {
			width: 100%;
		}
	}

	@keyframes hovering {
		0% {
			transform: translateY(6px);
		}

		50% {
			transform: translateY(-6px);
		}
		100% {
			transform: translateY(6px);
		}
	}
</style>