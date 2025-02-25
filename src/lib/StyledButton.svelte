<script>
	export let label;
	export let href;
	export let target = '_self';
</script>

<a {href} {target}>{label}</a>

<style>
	:root {
		--text: var(--black);
		--action: var(--primary);
	}

	a {
		text-decoration: none;

		color: var(--text);
		padding: 1rem;
		
        box-shadow: 0 0 0 2px var(--text) inset;
		transition: all 0.25s ease-in-out;

		width: max-content;
	}

	a:hover {
        box-shadow: 0 0 0 4px var(--action) inset;
	}
</style>
