<script>
	import Navbar from '$lib/Navbar.svelte';
</script>

<Navbar />
<slot></slot>

<style>
	:global(:root) {
		--white: #efefef;
		--black: #242424;
		--primary: #f3d305;

		--base-px: 2vw;
		--content-px: calc(3 * var(--base-px));
	}

	:global(body) {
		margin: 0;
		padding: 0;
		background-color: var(--white);
	}

	/* TODO txt outline (lanidng page "program" btn) */
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

	:global(.default-content-block){
		padding: var(--content-px);

		display: flex;
		flex-direction: column;
		align-items: start;
		justify-content: start;
		gap: 2rem;
	}
</style>
