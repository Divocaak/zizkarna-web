<script>
	export let src;
	export let srcBottom = null;
	export let imgsLeft = false;
	export let leftPanelFr = 1;
	export let rightPanelFr = 1;
	export let clr = 'var(--black)';
	export let bgClr = 'var(--white)';
</script>

<div
	class="wrapper"
	style="
		--left-panel: {leftPanelFr}fr;
		--right-panel: {rightPanelFr}fr;
		--color: {clr};
		--bg-color: {bgClr};"
>
	{#if !imgsLeft}<div class="default-content-block colored-block"><slot /></div>{/if}
	<div class="imgs-panel" class:two-images={srcBottom !== null}>
		<div class="img-container" style="background-image: url('{src}');"></div>
		{#if srcBottom}
			<div class="img-container" style="background-image: url('{srcBottom}');"></div>
		{/if}
	</div>
	{#if imgsLeft}<div class="default-content-block colored-block"><slot /></div>{/if}
</div>

<style>
	:root {
		--left-panel: 1fr;
		--right-panel: 1fr;
		--color: var(--black);
		--bg-color: var(--white);
	}

	.wrapper {
		position: relative;
		width: 100vw;
		height: 100vh;
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
	}

	.colored-block {
		color: var(--color);
		background-color: var(--bg-color);
	}
</style>
