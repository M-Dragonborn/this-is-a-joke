<script lang="ts">
    import Fa from 'svelte-fa';
    import { faUserAlt } from '@fortawesome/free-solid-svg-icons';
</script>

<h1 class="title-row">
    <Fa icon={faUserAlt} class="icon" />
    <span class="neon-blue">M_Drake (M)</span>
</h1>

<style>
    .title-row {
        display: flex;
        align-items: center;
        gap: 0.75rem;
    }
    .neon-blue {
        color: #02ffe1;
        font-size: 2.5rem;
        font-weight: bold;
        text-shadow: 0 0 8px #02ffe1, 0 0 16px #0084ff;
    }
    .title-row {
        font-size: 2.5rem;   /* Set the font size for both icon and text */
    }
</style>