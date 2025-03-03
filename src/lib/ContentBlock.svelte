<script>
	export let src;
	export let srcBottom = null;
	export let imgsLeft = false;
	export let leftPanelFr = 1;
	export let rightPanelFr = 1;
	export let clr = 'var(--black)';
	export let bgClr = 'var(--white)';
	export let gap = 2;
	export let contentPadding = 'inherit';
</script>

<div
	class="wrapper"
	style="
		--left-panel: {leftPanelFr}fr;
		--right-panel: {rightPanelFr}fr;
		--color: {clr};
		--bg-color: {bgClr};
		--gap: {gap}rem;
		--content-padding: {contentPadding}"
>
	{#if !imgsLeft}<div class="default-content-block content-block"><slot /></div>{/if}
	<div class="imgs-panel" class:two-images={srcBottom !== null}>
		<div class="img-container" style="background-image: url('{src}');"></div>
		{#if srcBottom}
			<div class="img-container" style="background-image: url('{srcBottom}');"></div>
		{/if}
	</div>
	{#if imgsLeft}<div class="default-content-block content-block"><slot /></div>{/if}
</div>

<style>
	:root {
		--left-panel: 1fr;
		--right-panel: 1fr;
		--color: var(--black);
		--bg-color: var(--white);
		--gap: 2rem;
		--content-padding: var(--content-px);
	}

	.wrapper {
		position: relative;
		width: 100vw;
		height: fit-content;
		min-height: 100vh;
		padding: 0 !important;
		margin: 0 !important;

		display: grid;
		grid-template-columns: var(--left-panel) var(--right-panel);
	}

	.imgs-panel {
		display: grid;
		grid-template-rows: 1fr;
	}
	.two-images {
		grid-template-rows: repeat(2, 1fr) !important;
	}

	.img-container {
		background-position: center;
		background-size: cover;
		background-repeat: none;
	}

	.content-block {
		width: calc(100% - 2 * var(--content-padding));
		color: var(--color);
		background-color: var(--bg-color);
		gap: var(--gap);
		padding: var(--content-padding);
	}

	@media (max-width: 575px) {
		.wrapper {
			grid-template-rows: repeat(2, 1fr);
			grid-template-columns: none;
		}
	}
</style>
