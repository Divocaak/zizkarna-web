<script>
	export let src;
	export let srcBottom = null;
	export let imgsLeft = false;

	export let mobileDesign = false;

	export let leftPanelFr = 1;
	export let rightPanelFr = 1;

	export let clr = 'var(--black)';
	export let bgClr = 'var(--white)';
	export let gap = 2;
	export let contentPadding = 'inherit';
</script>

<div
	class="wrapper"
	class:mobile-design={mobileDesign}
	style="
		--left-panel: {leftPanelFr}fr;
		--right-panel: {rightPanelFr}fr;
		--color: {clr};
		--bg-color: {bgClr};
		--gap: {gap}rem;
		--content-padding: {contentPadding}"
>
	{#if !imgsLeft}
		<div class="default-content-block content-block text-panel">
			<slot name="heading" class="heading" /><slot name="content" />
		</div>
	{/if}

	<div class="imgs-panel" class:two-images={srcBottom !== null}>
		<div class="mobile-heading">
			<slot name="heading" />
		</div>

		<div class="img-container" style="background-image: url('{src}');"></div>
		{#if srcBottom}
			<div class="img-container" style="background-image: url('{srcBottom}');"></div>
		{/if}
	</div>

	{#if imgsLeft}
		<div class="default-content-block content-block text-panel">
			<slot name="heading" class="heading" /><slot name="content" />
		</div>
	{/if}
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

		position: relative;
		min-height: 50vh;
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

	.mobile-heading {
		display: none;
	}

	@media (max-width: 575px) {
		.wrapper {
			grid-template-rows: repeat(2, 1fr);
			grid-template-columns: none;
		}

		.wrapper.mobile-design {
			grid-template-rows: auto auto;
			grid-template-columns: none;
		}

		.wrapper.mobile-design .imgs-panel {
			order: 1;
			position: relative;
		}

		.wrapper.mobile-design .text-panel {
			order: 2;
		}

		.wrapper.mobile-design .mobile-heading {
			display: flex;
			align-items: center;
			justify-content: center;

			position: absolute;
			inset: 0;

			padding: 2rem;
			color: white;
			z-index: 2;
			text-align: center;

			background: linear-gradient(to bottom, rgba(0, 0, 0, 0.35), rgba(0, 0, 0, 0.35));
		}

		:global(.wrapper.mobile-design .text-panel h1, .wrapper.mobile-design .text-panel p#landing) {
			display: none;
		}

		:global(.wrapper.mobile-design .text-panel p.primary) {
			text-align: center;
		}

		:global(.wrapper.mobile-design .text-panel p) {
			font-size: var(--fs-24);
		}
	}
</style>
