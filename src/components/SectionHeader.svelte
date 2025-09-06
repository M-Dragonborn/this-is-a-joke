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
    color: #02ffe1;
    font-size: 1rem;
    font-weight: bold;
    margin-bottom: .4rem;
}

.header-icon {
    color: #ffffff;
    font-size: 1.5rem;
}

.header-text {
    color: #02ffe1;
    font-size: 1.5rem;
    font-weight: bold;
}
</style>