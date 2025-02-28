<script>
	import { lang } from '$lib/stores/LangStore.js';
	import langs from '$lib/localization.json';
	import ContentBlock from '$lib/ContentBlock.svelte';
</script>

<ContentBlock src="/imgs/15.jpg" leftPanelFr={3} contentPadding={0}>
	<div class="wrapper">
		<div class="panel">
			<h1>{langs[$lang].venues.venues[3].label}</h1>
			<h2>{langs[$lang].venues.capacity}</h2>
			<p>2000+ {langs[$lang].venues.capacityUnits}</p>
		</div>
		<div class="panel">
			<h2>{langs[$lang].venues.operatingSeason}</h2>
			<p>{langs[$lang].venues.venues[3].operatingSeason}</p>
			<h2>{langs[$lang].venues.idealFor}</h2>
		</div>
	</div>
</ContentBlock>

<style>
	.wrapper {
		position: relative;
		width: 100%;
		height: 100%;
		padding: 0 !important;
		margin: 0 !important;

		background-color: red;

		display: grid;
		grid-template-columns: repeat(2, 1fr);
	}

	.panel {
		margin: var(--base-px);
		background-color: blue;
	}
</style>
