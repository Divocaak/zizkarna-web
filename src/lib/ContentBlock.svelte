<script>
	export let src;
	export let srcBottom = null;
	export let imgsLeft = false;
	export let imgsPanelWidth = 50;
</script>

<div class="wrapper">
	{#if !imgsLeft}<div class="panel"><slot /></div>{/if}
	<div class="panel imgs-panel" class:two-images={srcBottom !== null}>
		<div class="img-container" style="background-image: url('{src}');"></div>
		{#if srcBottom}
			<div class="img-container" style="background-image: url('{srcBottom}');"></div>
		{/if}
	</div>
	{#if imgsLeft}<div class="panel"><slot /></div>{/if}
</div>

<style>
	.wrapper {
		position: relative;
		width: 100vw;
		height: 100vh;
		padding: 0 !important;
		margin: 0 !important;

		/* align-items: center;
		justify-content: center;
		display: flex;
		flex-direction: row; */

		display: grid;
		grid-template-columns: 1fr 1fr;
	}

	.panel {
	}

	.panel.imgs-panel {
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
</style>
