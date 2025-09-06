<script>
  import { onMount } from "svelte";
  import '../app.css';
  import M from '$lib/assets/M.svg';

  let { children } = $props();

  onMount(() => {
    // Wait for particles.js to load
    const loadParticles = () => {
      if (window.particlesJS) {
        window.particlesJS.load("particles-js", "/particles.json", () => {
          console.log("callback - particles.js config loaded");
        });
      } else {
        console.error("particlesJS is not loaded");
      }
    };

    // If the script is already loaded
    if (window.particlesJS) {
      loadParticles();
    } else {
      // Dynamically load the script
      const script = document.createElement("script");
      script.src = "https://cdn.jsdelivr.net/npm/particles.js@2.0.0/particles.min.js";
      script.onload = loadParticles;
      document.body.appendChild(script);
    }
  });
</script>

<svelte:head>
  <link rel="icon" href={M} />
  <title>M_Dragonborn</title>
</svelte:head>

<!-- Full-screen particles container -->
<div style="
      position: fixed;
      top: 0;
      left: 0;
      width: 100vw;
      height: 100vh;
      z-index: 0;
      opacity: 0.5;
      pointer-events: none;
    ">
  <div id="particles-js" style="width: 100%; height: 100%;"></div>
</div>

<!-- Render the rest of your page content on top -->
<div style="position: relative; z-index: 1;">
  {@render children?.()}
</div>
