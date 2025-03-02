<script>
	import { lang } from '$lib/stores/LangStore.js';
	import langs from '$lib/localization.json';
	export let label;
	export let mail;
	export let name = null;
	export let mailSecondary = null;
</script>

<div>
	<p>{label}</p>
	{#if name}<p>{name}</p>{:else}<br />{/if}
	<a href="mailto:{mail}" class="text-link-fx">{mail}</a>
	{#if mailSecondary}<a href="mailto:{mailSecondary}" class="text-link-fx">{mailSecondary}</a>{/if}
</div>

<style>
	a,
	p {
		font-weight: 400;
		font-size: var(--fs-24);
		line-height: 32px;

		margin: 0;
	}

	p:first-of-type {
		font-weight: 800;
	}

	a {
		font-weight: 400;
		text-align: end;
	}

	div {
		display: grid;
		grid-template-columns: repeat(2, 1fr);
		grid-template-rows: auto auto;
		grid-auto-flow: column;

		border-top: 1px solid var(--black);

		padding-top: 0.5rem;
		padding-bottom: 1rem;
	}

	@media (max-width: 575px) {
		div {
			display: block;
		}
	}
</style>
