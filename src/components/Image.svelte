<script lang="ts">
	import { onMount } from 'svelte';

	let container: HTMLDivElement;
	let cursor: HTMLDivElement;
	let altImage: HTMLDivElement;
	let mainImage: HTMLImageElement;
	let active = false;

	let mouseX = 0;
	let mouseY = 0;
	let posX = 0;
	let posY = 0;

	onMount(() => {
		altImage = container.querySelector('.alt-image') as HTMLDivElement;
		mainImage = container.querySelector('.main-image') as HTMLImageElement;

		// Set altImage height to match main image
		altImage.style.width = `${mainImage.offsetWidth}px`;
		altImage.style.height = `${mainImage.offsetHeight}px`;

		const move = (e: MouseEvent) => {
			if (!active) return;
			const rect = container.getBoundingClientRect();
			mouseX = e.clientX - rect.left;
			mouseY = e.clientY - rect.top;
		};

		const animate = () => {
			posX += (mouseX - posX) * 0.15;
			posY += (mouseY - posY) * 0.15;

			if (cursor) cursor.style.left = `${posX}px`;
			if (cursor) cursor.style.top = `${posY}px`;

			if (altImage) altImage.style.clipPath = `circle(40px at ${posX}px ${posY}px)`;

			requestAnimationFrame(animate);
		};

		animate();

		const enter = () => {
			active = true;
			if (cursor) cursor.style.display = 'block';
		};

		const leave = () => {
			active = false;
			if (cursor) cursor.style.display = 'none';
			if (altImage) altImage.style.clipPath = `circle(0px at 0 0)`;
		};

		container.addEventListener('mouseenter', enter);
		container.addEventListener('mouseleave', leave);
		container.addEventListener('mousemove', move);
	});
</script>

<div class="profile-container" bind:this={container}>
	<!-- Main image at bottom -->
	<img src="pfpmain.webp" alt="Profile" class="main-image" />

	<!-- Alternate image on top -->
	<div class="alt-image"></div>

	<!-- Invisible cursor tracker -->
	<div class="cursor-mask" bind:this={cursor}></div>
</div>

<style lang="scss">
	.profile-container {
		position: relative;
		display: inline-block;
	}

	.main-image {
		width: 1350px;
		border-radius: 20px;
		cursor: none;
		display: block;
		@media (max-width: 505px) {
			width: 100%;
		}
	}

	.alt-image {
		position: absolute;
		top: 0;
		left: 0;
		border-radius: 20px;
		background-image: url('alt-image.webp');
		background-size: 100% 100%; /* Match main image exactly */
		background-position: top left;
		clip-path: circle(0px at 0 0);
		pointer-events: none;
		transition: clip-path 0s;
	}

	.cursor-mask {
		position: absolute;
		width: 80px;
		height: 80px;
		pointer-events: none;
		display: none;
		transform: translate(-50%, -50%);
	}
</style>
