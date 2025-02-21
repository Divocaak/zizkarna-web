<script>
	import ContentBlock from '$lib/ContentBlock.svelte';
	import ImageBlock from '$lib/ImageBlock.svelte';
	import StyledButton from '$lib/StyledButton.svelte';
</script>

<ImageBlock src="/imgs/7.jpg">
	<!-- TODO shadows? -->
	<svg
		class="logo"
		xmlns="http://www.w3.org/2000/svg"
		viewBox="0 0 52.39 159.74"
		fill="var(--white)"
	>
		<polygon
			points="0.31 22.34 0.31 29.65 48.98 29.65 0.31 80.78 0.31 94.69 49.02 94.69 0.31 145.86 0.31 159.74 52.08 159.74 52.08 152.43 2.88 152.43 52.08 101.18 52.08 87.39 2.85 87.39 52.08 36.1 52.08 22.34 0.31 22.34"
		/>
		<rect width="52.39" height="6.67" />
	</svg>
	<p class="catch-phrase">Kulturní oáza<br />v centru<br />Českých Budějovic</p>
</ImageBlock>
<ContentBlock src="/imgs/5.jpg">
	<h1>O Žižkárně</h1>
	<p>lorem pisum</p>
	<StyledButton href="about" label="Chci vědět víc!" />
</ContentBlock>
<!-- <ContentBlock src="/imgs/5.jpg" srcBottom="/imgs/6.jpg" imgsLeft={true}></ContentBlock> -->
<ImageBlock src="/imgs/20.jpg">
	<a href="/programme" class="text-link-fx inverted">program</a>
</ImageBlock>

<style>
	svg.logo {
		height: 30%;
	}

	.catch-phrase {
		color: var(--white);
	}
</style>
