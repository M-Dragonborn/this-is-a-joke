<script lang="ts">
	import { onMount } from 'svelte';

	export let altSrc: string = '/alt-image.webp';

	let container: HTMLDivElement;
	let cursor: HTMLDivElement;
	let altImage: HTMLDivElement;
	let mainImage: HTMLImageElement;
	let active = false;

	let mouseX = 0, mouseY = 0;
	let posX = 0, posY = 0;

	onMount(() => {
		altImage = container.querySelector('.alt-image') as HTMLDivElement;
		mainImage = container.querySelector('.main-image') as HTMLImageElement;

		const updateAltImageSize = () => {
			const rect = mainImage.getBoundingClientRect();
			altImage.style.width = `${rect.width}px`;
			altImage.style.height = `${rect.height}px`;
			altImage.style.top = `${mainImage.offsetTop}px`;
			altImage.style.left = `${mainImage.offsetLeft}px`;
		};

		updateAltImageSize();
		window.addEventListener('resize', updateAltImageSize);

		const move = (e: MouseEvent) => {
			if (!active) return;
			const rect = container.getBoundingClientRect();
			mouseX = e.clientX - rect.left;
			mouseY = e.clientY - rect.top;
		};

		const animate = () => {
			posX += (mouseX - posX) * 0.15;
			posY += (mouseY - posY) * 0.15;

			cursor?.style.setProperty('left', `${posX}px`);
			cursor?.style.setProperty('top', `${posY}px`);
			altImage?.style.setProperty('clip-path', `circle(40px at ${posX}px ${posY}px)`);

			requestAnimationFrame(animate);
		};

		animate();

		const enter = () => {
			active = true;
			cursor && (cursor.style.display = 'block');
		};

		const leave = () => {
			active = false;
			cursor && (cursor.style.display = 'none');
			altImage && (altImage.style.clipPath = 'circle(0px at 0 0)');
		};

		container.addEventListener('mouseenter', enter);
		container.addEventListener('mouseleave', leave);
		container.addEventListener('mousemove', move);

		return () => window.removeEventListener('resize', updateAltImageSize);
	});
</script>

<div class="profile-container" bind:this={container}>
	<img src="/pfpmain.webp" alt="Profile" class="main-image" />
	<div class="alt-image" style="background-image: url({altSrc})"></div>
	<div class="cursor-mask" bind:this={cursor}></div>
</div>

<style lang="scss">
.profile-container {
	position: relative;
	display: inline-block;
}

.main-image {
	width: 1650px;
	border-radius: 20px;
	cursor: none;
	display: block;
	animation: hovering 2.5s ease-in-out infinite;

	@media (max-width: 505px) {
		width: 100%;
	}
}

.alt-image {
	position: absolute;
	top: 0;
	left: 0;
	border-radius: 20px;
	background-size: cover;
	background-position: center;
	clip-path: circle(0px at 0 0);
	pointer-events: none;
}

.cursor-mask {
	position: absolute;
	width: 80px;
	height: 80px;
	pointer-events: none;
	display: none;
	transform: translate(-50%, -50%);
}

@keyframes hovering {
	0% { transform: translateY(6px); }
	50% { transform: translateY(-6px); }
	100% { transform: translateY(6px); }
}
</style>
