<script>
	import { lang } from '$lib/stores/LangStore.js';
	import langs from '$lib/localization.json';
	export let label;
	export let mail;
	export let name = null;
	export let mailSecondary = null;
</script>

<div>
	<b>{label}</b>
	{#if name}<p>{name}</p>{/if}
	<a href="mailto:{mail}" class="text-link-fx">{mail}</a>
	{#if mailSecondary}<a href="mailto:{mailSecondary}" class="text-link-fx">{mailSecondary}</a>{/if}
</div>

<style>
	a,
	b,
	p {
		margin: 0;
	}

	div {
		display: grid;
		grid-template-columns: repeat(2, 1fr);
		grid-template-rows: auto auto;
		grid-auto-flow: column;
		border-top: 2px solid var(--black);
	}
</style>
