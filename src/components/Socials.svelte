<script lang="ts">
	import { faLink, faEnvelope, faChessKnight, faGamepad, faI } from '@fortawesome/free-solid-svg-icons';
	import {
		faDiscord,
		faFacebook,
		faGithub,
		faInstagram,
		faInstagramSquare,
		faReddit,
		faTelegramPlane,
		faTwitter,
		faYoutube
	} from '@fortawesome/free-brands-svg-icons';
	import SectionHeader from '../components/SectionHeader.svelte';
	import Social from '../components/Social.svelte';
</script>

<section>
	<SectionHeader icon={faLink}  text="Socials" />
	<ul>

		<Social
			faIcon={faDiscord}
			link="https://discord.com/users/540170296406179851"
			anchor="discord"
			overrideText="M_Dragonborn"
		/>
		<Social
			faIcon={faFacebook}
			link="https://www.facebook.com/M.Dragonborn"
			anchor="Facebook"
		/>
		<Social
			faIcon={faInstagram}
			link="https://www.instagram.com/m_dragonborn_/"
			anchor="Instagram"
		/>		
		<Social faIcon={faGithub} link="https://github.com/M-Dragonborn" anchor="github" />
		<Social faIcon={faTelegramPlane} link="https://t.me/MDragonborn" anchor="telegram" />
		<Social
			faIcon={faYoutube}
			link="https://www.youtube.com/@mdragonborn"
			anchor="youtube"
		/>
		<Social faIcon={faGamepad} link="https://steamcommunity.com/id/M-Dragonborn/" anchor="Steam" />
		<Social faIcon={faChessKnight} link="https://www.chess.com/member/m_dragonborn" anchor="chess" />
		<Social
			faIcon={faEnvelope}
			link="mailto:musfiqdrake@gmail.com"
			anchor="mail"
			overrideText="musfiqdrake@gmail.com"
		/>
	</ul>
</section>

<style lang="scss">
	ul {
		list-style: none;
	}
</style>