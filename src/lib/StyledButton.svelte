<script>
	export let label;
	export let href;
	export let target = '_self';
	export let textClr = 'var(--black)';
	export let actionClr = 'var(--primary)';
</script>

<a {href} {target} style="--text: {textClr}; --action: {actionClr};">{label}</a>

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

		font-style: normal;
		font-variant: normal;
		font-weight: 300;
		font-size: var(--fs-24);
		line-height: 31px;
	}

	a:hover {
		box-shadow: 0 0 0 4px var(--action) inset;
	}

	@media (max-width: 575px) {
		a{
			width: fit-content;
			text-align: center;
		}
	}
</style>
