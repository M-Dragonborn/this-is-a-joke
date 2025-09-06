<script lang="ts">
	import { faAddressCard } from '@fortawesome/free-solid-svg-icons';
	import SectionHeader from '../components/SectionHeader.svelte';
</script>

<section>
	<SectionHeader icon={faAddressCard} text="About Me" />
	<p>
		Hello there! My name is <span class="highlight">M Drake</span> or
		<span class="highlight">Musfiqur Rahman</span>. I'm a 22-year-old
		<span class="highlight">computer science</span>
		student living in
		<a class="highlight2" href="https://share.google/ECstOJK7uDGoRZqMQ">Dhaka, Bangladesh</a>,
		studying at <a class="highlight2" href="https://bubt.edu.bd/">BUBT</a>.<br />
		My primary career is managing <span class="highlight" >Crescent International</span>, which is an industrial machinery manufacturing company here in Bangladesh. As a
		hobby, I work on various open-source community projects, and I also do freelance work periodically.
		I am a gamer & an audiophile who is currently learning programming a bit too seriously. I have knowledge
		in a few different programming languages like
		<span class="highlight">Python</span>,
		<span class="highlight">C</span>, <span class="highlight">HTML</span>, and
		<span class="highlight">CSS</span>, with the first being my most used and the last being my
		least used language.<br /> You can see some of the video games I play on my
		<a class="highlight2" href="#steam">Steam</a> account. In addition, I also play
		<a class="highlight2" href="#chess">chess</a>
		and
		<a class="highlight1" href="https://en.wikipedia.org/wiki/Dungeons_%26_Dragons"
			>Dungeons and Dragons</a
		>.
		<a class="highlight1" href="https://en.wikipedia.org/wiki/The_Elder_Scrolls_V:_Skyrim">Skyrim</a
		>,
		<a class="highlight1" href="https://en.wikipedia.org/wiki/The_Witcher_(video_game_series)"
			>the Witcher trilogy</a
		>, and
		<a class="highlight1"href="https://en.wikipedia.org/wiki/Dark_Souls">Dark Souls</a> are a few of my favorite games. I also enjoy reading,
		and
		<a class="highlight1" href="https://en.wikipedia.org/wiki/A_Song_of_Ice_and_Fire">the Song of Ice and Fire</a>
		collection is one of my favorites.<br /> (You can probably figure out the obsession with dragons
		by now).<br />
		I almost always have music playing in the background while I work or game. I have learned audio engineering and sound design from a friend of mine who runs a production studio in <a class="highlight1"href="https://en.wikipedia.org/wiki/Hollywood">Hollywood</a>.<br/>
		I generally hang around on
		<a class="highlight2" href="#discord">Discord</a>, but you can probably find me via
		<a class="highlight2" href="#mail">mail</a>.
	</p>
</section>

<style>
	a {
		white-space: nowrap;
	}

	p {
		text-align: justify;
	}
	.highlight {
		color: #48a0ff;
	}
	.highlight1 {
		color: #48a0ff;
	}
	.highlight1:hover {
		color: #02ffe1;
		text-shadow:
			0 0 8px #02ffe1,
			0 0 16px #0084ff;
	}
	.highlight2 {
		color: #48a0ff;
		font-weight: bold;
	}
	.highlight2:hover {
		color: #02ffe1;
		text-shadow:
			0 0 8px #02ffe1,
			0 0 16px #0084ff;
	}
</style>
