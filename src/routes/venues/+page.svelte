<script>
	import { lang } from '$lib/stores/LangStore.js';
	import langs from '$lib/localization.json';
	import ImageBlock from '$lib/ImageBlock.svelte';
	import ContentBlock from '$lib/ContentBlock.svelte';
	import StyledButton from '$lib/StyledButton.svelte';
</script>

<ImageBlock src="/imgs/20.jpg">
	<h1 class="primary">{langs[$lang].venues.heading}</h1>
</ImageBlock>
<ContentBlock src="/imgs/19.jpg" srcBottom="/imgs/3.jpg" clr="var(--primary)">
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
	<StyledButton href="/contacts" label={langs[$lang].venues.btn} />
</ContentBlock>
<ContentBlock
	src="/imgs/12.jpg"
	srcBottom="/imgs/13.jpg"
	clr="var(--white)"
	bgClr="var(--secondary)"
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
	<StyledButton href="/contacts" label={langs[$lang].venues.btn} />
</ContentBlock>
<ContentBlock
	src="/imgs/5.jpg"
	srcBottom="/imgs/18.jpg"
	imgsLeft={true}
	clr="var(--white)"
	bgClr="var(--black)"
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
	<StyledButton href="/contacts" label={langs[$lang].venues.btn} />
</ContentBlock>
<ContentBlock src="/imgs/17.jpg" srcBottom="/imgs/2.jpg" imgsLeft={true}>
	<h1>{langs[$lang].venues.venues[2].label}</h1>
	<h2>{langs[$lang].venues.capacity}</h2>
	<p>2000+ {langs[$lang].venues.capacityUnits}</p>
	<h2>{langs[$lang].venues.operatingSeason}</h2>
	<p>{langs[$lang].venues.venues[2].operatingSeason}</p>
	<h2>{langs[$lang].venues.idealFor}</h2>
	{#each langs[$lang].venues.venues[2].idealFor as text}
		<p>{text}</p>
	{/each}
	<StyledButton href="/contacts" label={langs[$lang].venues.btn} />
</ContentBlock>
