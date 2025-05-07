<script>
	import { lang } from '$lib/stores/LangStore.js';
	import langs from '$lib/localization.json';
	import ImageBlock from '$lib/ImageBlock.svelte';
	import ContentBlock from '$lib/ContentBlock.svelte';
	import StyledButton from '$lib/StyledButton.svelte';
</script>

<svelte:head>
	<script type="application/ld+json">
		{
			"@context": "https://schema.org",
			"@graph": [
				{
					"@type": "EventVenue",
					"name": "Vnitřní tančírna a Bar",
					"description": "Univerzální prostor ideální pro Malý koncert, Klubovou noc / Party, Přednášku, Divadlo, Slam poetry",
					"url": "https://zizkarna.cz/venues",
					"maximumAttendeeCapacity": 150,
					"event": ["MusicEvent", "TheaterEvent". "Party", "Lecture"]
				},
				{
					"@type": "EventVenue",
					"name": "Garáž",
					"description": "Univerzální prostor ideální pro Střední koncert, Ted-Talks, Divadlo, Slam Poetry, Větší party, Design market",
					"url": "https://zizkarna.cz/venues",
					"maximumAttendeeCapacity": 350,
					"event": ["MusicEvent", "TheaterEvent", "Party", "Market", "Lecture", "ScreeningEvent", "ExhibitionEvent"]
				},
				{
					"@type": "EventVenue",
					"name": "Násypka",
					"description": "Venkovní stage určena pro Větší koncert, Ted-Talks, Divadlo, Slam Poetry, Trhy / Street Food Market, Letní kino",
					"url": "https://zizkarna.cz/venues",
					"maximumAttendeeCapacity": 600,
					"event": ["MusicEvent", "TheaterEvent", "Lecture", "Market", "ScreeningEvent", "Festival", "ExhibitionEvent"]
				},
				{
					"@type": "EventVenue",
					"name": "Buzerplatz",
					"description": "Areál Žižkárny použitelný pro Velké koncerty, Divadlo, Trhy / Street Food Market, Velké venkovní kino, Živý přenos sportovních utkání",
					"url": "https://zizkarna.cz/venues",
					"maximumAttendeeCapacity": 2000,
					"event": ["MusicEvent", "TheaterEvent", "Festival", "FoodEvent", "ScreeningEvent", "SportsEvent", "ExhibitionEvent"]
				}
			]
		}
	</script>
</svelte:head>

<ImageBlock src="/imgs/2.jpg">
	<h1 class="primary">{langs[$lang].venues.heading}</h1>
</ImageBlock>
<ContentBlock src="/imgs/19.jpg" srcBottom="/imgs/3.jpg" bgClr="var(--primary)" gap={0.5}>
	<h1>{langs[$lang].venues.venues[0].label}</h1>
	<h2>{langs[$lang].venues.capacity}</h2>
	<p>{langs[$lang].venues.capacityStanding}: 120 {langs[$lang].venues.capacityUnits}</p>
	<p>{langs[$lang].venues.capacitySitting}: 50 {langs[$lang].venues.capacityUnits}</p>
	<h2>{langs[$lang].venues.operatingSeason}</h2>
	<p>{langs[$lang].venues.venues[0].operatingSeason}</p>
	<h2>{langs[$lang].venues.idealFor}</h2>
	{#each langs[$lang].venues.venues[0].idealFor as text}
		<p>{text}</p>
	{/each}
	<StyledButton href="/contacts" label={langs[$lang].venues.btn} actionClr="var(--black)" />
</ContentBlock>
<ContentBlock
	src="/imgs/12.jpg"
	srcBottom="/imgs/13.jpg"
	clr="var(--white)"
	bgClr="var(--secondary)"
	gap={0.5}
	imgsLeft={true}
>
	<h1>{langs[$lang].venues.venues[1].label}</h1>
	<h2>{langs[$lang].venues.capacity}</h2>
	<p>{langs[$lang].venues.capacityStanding}: 350 {langs[$lang].venues.capacityUnits}</p>
	<p>{langs[$lang].venues.capacitySitting}: 150 {langs[$lang].venues.capacityUnits}</p>
	<h2>{langs[$lang].venues.operatingSeason}</h2>
	<p>{langs[$lang].venues.venues[1].operatingSeason}</p>
	<h2>{langs[$lang].venues.idealFor}</h2>
	{#each langs[$lang].venues.venues[1].idealFor as text}
		<p>{text}</p>
	{/each}
	<StyledButton
		href="/contacts"
		label={langs[$lang].venues.btn}
		textClr="var(--white)"
		actionClr="var(--primary)"
	/>
</ContentBlock>
<ContentBlock
	src="/imgs/5.jpg"
	srcBottom="/imgs/18.jpg"
	clr="var(--white)"
	bgClr="var(--black)"
	gap={0.5}
>
	<h1>{langs[$lang].venues.venues[2].label}</h1>
	<h2>{langs[$lang].venues.capacity}</h2>
	<p>600 {langs[$lang].venues.capacityUnits}</p>
	<h2>{langs[$lang].venues.operatingSeason}</h2>
	<p>{langs[$lang].venues.venues[2].operatingSeason}</p>
	<h2>{langs[$lang].venues.idealFor}</h2>
	{#each langs[$lang].venues.venues[2].idealFor as text}
		<p>{text}</p>
	{/each}
	<StyledButton href="/contacts" label={langs[$lang].venues.btn} textClr="var(--white)" />
</ContentBlock>
<ContentBlock src="/imgs/17.jpg" srcBottom="/imgs/1.jpg" gap={0.5} imgsLeft={true}>
	<h1>{langs[$lang].venues.venues[3].label}</h1>
	<h2>{langs[$lang].venues.capacity}</h2>
	<p>2000+ {langs[$lang].venues.capacityUnits}</p>
	<h2>{langs[$lang].venues.operatingSeason}</h2>
	<p>{langs[$lang].venues.venues[3].operatingSeason}</p>
	<h2>{langs[$lang].venues.idealFor}</h2>
	{#each langs[$lang].venues.venues[3].idealFor as text}
		<p>{text}</p>
	{/each}
	<StyledButton href="/contacts" label={langs[$lang].venues.btn} />
</ContentBlock>

<style>
	p {
		margin: 0;
	}

	h2 {
		margin-bottom: 0;
	}

	h1 {
		font-weight: 800;
		text-transform: uppercase;
	}

	h1.primary {
		font-size: var(--fs-150);
		line-height: 184px;
	}

	h1:not(.primary) {
		font-size: var(--fs-72);
		line-height: 85px;
		margin: 0;
	}

	h2,
	p {
		font-weight: 300;
		font-size: var(--fs-32);
		line-height: 37px;
	}

	h2 {
		font-weight: 800;
	}

	p:last-of-type {
		padding-bottom: 5rem;
	}

	@media (max-width: 575px) {
		h1.primary {
			font-size: var(--fs-72);
			line-height: 75px;
			text-align: center;
		}

		h1:not(.primary) {
			font-size: var(--fs-48);
			line-height: 55px;
		}
	}
</style>
