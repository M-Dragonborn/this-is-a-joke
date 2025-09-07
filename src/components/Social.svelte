<script lang="ts">
    import Fa from 'svelte-fa';
    import type { IconDefinition } from '@fortawesome/free-brands-svg-icons';

    export let faIcon: IconDefinition;
    export let anchor: string;
    export let link: string;
    export let overrideText: string | boolean = false;
</script>

<li id={anchor} class="social">
    <div class="icon">
        <Fa icon={faIcon} />
	</div>
    <a href={link} class="neon-blue">{overrideText ? overrideText : 'M_drake.me/#' + anchor}</a>
</li>

<style lang="scss">
    .social {
        display: flex;
        gap: 0.2rem;
		font-size:1rem;
        align-items: center;
        padding:.3rem;

        a:hover {
            color: var(--white);
        }
    }

    .icon {
        text-align: center;
        width: 1.2rem;
    }

    .social:hover {
        color: #0084ff;
        animation-name: pulse;
        animation-duration: 1s;
        animation-fill-mode: forwards;
        animation-iteration-count: infinite;
        border-radius: 8px;
    }

	.neon-blue{
		color: #007bff;
		text-shadow: 0 0 8px #141515, 0 0 16px #0011ff;
	}

    @keyframes pulse {
        0% {
            box-shadow: 0 0 0 0 #0084ff;
        }
        70% {
            box-shadow: 0 0 10px 10px rgba(0, 132, 255, 0);
        }
        100% {
            box-shadow: 0 0 0 0 rgba(0, 132, 255, 0);
        }
    }
</style>