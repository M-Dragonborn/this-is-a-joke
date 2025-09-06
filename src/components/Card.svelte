<script lang="ts">
	import Image from '../components/Image.svelte';
	import Title from '../components/Title.svelte';
	import About from '../components/About.svelte';
	import Socials from './Socials.svelte';
</script>
<div id="particles-js"></div>
<div class="card-center">
	<div id="card">
		<div id="image">
			<Image />
		</div>
		<div id="card-container">
			<Title />
			<div id="components">
			<Socials />
			<About />
			</div>
		</div>
	</div>
</div>
<style lang="scss">

	.card-center {
    display: flex;
    justify-content: center;
    align-items: center;
    min-height: 100vh;
    width: 100vw;
	}
	#card,
	#components {
		gap: 1rem;
		display: flex;
		flex-direction: row;
	}

	#card-container {
		display: flex;
		flex-direction: column;
		justify-content: space-evenly;
	}

	#image {
		transition: margin 1s ease;
		margin-left: -100px;
		margin-top: -50px;
		margin-right: 20px;
	}

	#card {
		border-radius: 15px;
		padding: 25px;
		max-width: 1450px;
		background: #131313eb;
		box-shadow: 0 0 8px #02ffe1, 0 0 30px #0084ff;

		// Full HD
		@media (max-width: 1800px) {
			max-width: 1300px;
		}

		// Mobile
		@media (max-width: 505px) {
			border-radius: 0;
			width: initial !important;
		}

		// Mobile
		@media (min-width: 506px) {
			max-height: 85vh; // Prevents overflow when screen height is too small.
		}
	}

	// Less then Full HD
	@media (max-width: 1550px) {
		#image {
			margin: 0;
		}

		#card {
			overflow: auto; // Allows scrolling when screen height is too small.
			width: min-content;
		}

		#components,
		#card {
			flex-direction: column;
		}
	}
</style>