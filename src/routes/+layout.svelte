<script>
	import Analytics from '$lib/Analytics.svelte';
	import Navbar from '$lib/Navbar.svelte';
</script>

<Navbar />
<!-- TODO add logo overlays on pages -->
<!-- landing -->
<!-- about -->
<!-- contacts -->
<slot></slot>
<Analytics />

<style>
	@font-face {
		font-family: 'NeueMachina';
		src: url('/fonts/NeueMachina-Light.otf') format('opentype');
		font-weight: 300;
	}

	@font-face {
		font-family: 'NeueMachina';
		src: url('/fonts/NeueMachina-Regular.otf') format('opentype');
		font-weight: 400;
	}

	@font-face {
		font-family: 'NeueMachina';
		src: url('/fonts/NeueMachina-Ultrabold.otf') format('opentype');
		font-weight: 800;
	}

	:global(:root) {
		--white: #efefef;
		--black: #242424;
		--primary: #f3d305;
		--secondary: #5a01da;
		--zlab-primary: #ff5500;

		--base-px: 2vw;
		--content-px: calc(3 * var(--base-px));

		/* vw = px value / 19.2 */
		/* rem = px value / 16 */
		--fs-12: clamp(12px, 0.625vw, 1rem);
		--fs-14: clamp(14px, 0.73vw, 1.25rem);
		--fs-16: clamp(16px, 0.83vw, 1.5rem);
		--fs-18: clamp(18px, 0.94vw, 1.75rem);
		--fs-20: clamp(20px, 1.04vw, 2rem);
		--fs-24: clamp(24px, 1.25vw, 2.5rem);
		--fs-32: clamp(32px, 1.67vw, 3rem);
		--fs-48: clamp(48px, 2.5vw, 3rem);
		--fs-64: clamp(64px, 3.33vw, 4rem);
		--fs-72: clamp(72px, 3.75vw, 4.5rem);
		--fs-150: clamp(150px, 9.81vw, 9.37rem);
	}

	:global(body) {
		margin: 0;
		padding: 0;

		background-color: var(--white);

		font-family: 'NeueMachina', sans-serif;
		letter-spacing: 0px;
		font-style: normal;
		font-variant: normal;
	}
	:global(html) {
		scroll-behavior: smooth;
	}

	:global(.text-link-fx) {
		color: var(--black);
		text-decoration: none;

		transition: all 0.2s ease-in-out;
	}
	:global(.text-link-fx:hover, .text-link-fx.active) {
		color: var(--primary);
	}
	:global(.text-link-fx.inverted) {
		color: var(--primary);
	}
	:global(.text-link-fx.inverted:hover, .text-link-fx.inverted.active) {
		color: var(--white);
	}

	:global(.default-content-block) {
		padding: var(--content-px);

		display: flex;
		flex-direction: column;
		align-items: start;
		justify-content: start;
		gap: 2rem;
	}

	:global(.primary) {
		color: var(--primary);
	}

	:global(.secondary) {
		color: var(--secondary);
	}
</style>
