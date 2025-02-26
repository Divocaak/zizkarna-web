<script>
	import { lang } from '$lib/stores/LangStore.js';
	import langs from '$lib/localization.json';
	import ContentBlock from '$lib/ContentBlock.svelte';
</script>

<ContentBlock src="/imgs/11.jpg">
	<h1>{langs[$lang].about[0].heading}</h1>
	<p class="primary">{langs[$lang].about[0].sub}</p>
	{#each langs[$lang].about[0].texts as text}
		<p>{text}</p>
	{/each}
</ContentBlock>
<ContentBlock src="/imgs/16.jpg" imgsLeft={true}>
	<h1>{langs[$lang].about[1].heading}</h1>
	{#each langs[$lang].about[1].texts as text}
		<p>{text}</p>
	{/each}
</ContentBlock>
<ContentBlock src="/imgs/0.jpg">
	<h1>{langs[$lang].about[2].heading}</h1>
	{#each langs[$lang].about[2].texts as text}
		<p>{text}</p>
	{/each}
</ContentBlock>
