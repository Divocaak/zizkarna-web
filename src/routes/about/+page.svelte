<script>
	import { lang } from '$lib/stores/LangStore.js';
	import langs from '$lib/localization.json';
	import ContentBlock from '$lib/ContentBlock.svelte';
</script>

<svelte:head>
	<script type="application/ld+json">
		{
			"@context": "https://schema.org",
			"@type": "Organization",
			"name": "Žižkárna",
			"url": "https://zizkarna.cz/about",
			"description": "Žižkárna je kulturní prostor v Českých Budějovicích, který nabízí jedinečnou atmosféru starých kasáren. Spojuje generace a profese a umožňuje rozvíjet kulturní potenciál každého.",
			"foundingDate": "2019",
			"address": {
				"@type": "PostalAddress",
				"addressLocality": "České Budějovice",
				"addressCountry": "CZ"
			},
			"sameAs": "https://zizkarna.cz",
			"mainEntityOfPage": "https://zizkarna.cz/about"
		}
	</script>
</svelte:head>

<ContentBlock src="/imgs/11.jpg">
	<h1>{langs[$lang].about[0].heading}</h1>
	<p class="primary">{langs[$lang].about[0].sub}</p>
	{#each langs[$lang].about[0].texts as text}
		<p>{text}</p>
	{/each}
</ContentBlock>
<ContentBlock src="/imgs/16.jpg" imgsLeft={true}>
	<h1 class="secondary">{langs[$lang].about[1].heading}</h1>
	{#each langs[$lang].about[1].texts as text}
		<p>{text}</p>
	{/each}
</ContentBlock>
<ContentBlock src="/imgs/0.jpg">
	<h1 class="primary">{langs[$lang].about[2].heading}</h1>
	{#each langs[$lang].about[2].texts as text}
		<p>{text}</p>
	{/each}
</ContentBlock>

<style>
	h1 {
		font-weight: 800;
		font-size: var(--fs-64);
		line-height: 70px;
		text-transform: uppercase;
	}

	p {
		font-weight: 300;
		font-size: var(--fs-32);
		line-height: 40px;

		padding: 0;
		margin: 0;
	}

	p.primary {
		font-weight: 800;
		text-transform: uppercase;
	}

	@media (max-width: 575px) {
		h1 {
			font-size: var(--fs-48);
			line-height: 55px;
		}
	}
</style>
