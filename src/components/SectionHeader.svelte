<script lang="ts">
    export let icon;
    export let text: string;
    import Fa from 'svelte-fa';
</script>

<h2 class="section-header">
    <span class="header-icon"><Fa icon={icon} /></span>
    <span class="header-text">{text}</span>
</h2>

<style>
.section-header {
    display: flex;
    align-items: center;
    gap: 0.5rem;
    margin-bottom: 0.4rem;
    font-weight: bold;
    flex-wrap: wrap; /* wrap if container is narrow */
}

.header-icon {
    color: #ffffff;
    font-size: clamp(1rem, 2vw, 1.5rem); /* fluid scaling */
    flex-shrink: 0; /* prevents icon from shrinking */
    display: flex; /* ensures proper alignment */
    align-items: center;
}

.header-text {
    color: #02ffe1;
    font-size: clamp(1.5rem, 2.5vw, 1.75rem); /* fluid scaling */
    word-break: break-word;
}
</style>
