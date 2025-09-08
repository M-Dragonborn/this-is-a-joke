<script lang="ts">
    import Fa from 'svelte-fa';
    import { faUserAlt } from '@fortawesome/free-solid-svg-icons';
</script>

<h1 class="title-row">
    <Fa icon={faUserAlt} />
    <span class="neon-blue">M_Drake (M)</span>
</h1>

<style>
.title-row {
    display: flex;
    align-items: center;
    gap: 0.75rem;
    font-size: 2.5rem; /* Font size for both icon and text */
}

.neon-blue {
    color: #02ffe1;
    font-weight: bold;
    text-shadow: 0 0 8px #02ffe1, 0 0 16px #0084ff;
}

/* optional hover glow */
.title-row:hover .neon-blue {
    text-shadow: 0 0 12px #000000, 0 0 24px #0084ff;
}
</style>