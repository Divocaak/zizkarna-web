<script>
	import { blur, fade } from 'svelte/transition';
	import { page } from '$app/stores';
	import { lang } from '$lib/stores/LangStore.js';
	import langs from '$lib/localization.json';

	let menuShown = false;
	const showMenu = (newVal) => (menuShown = newVal);
</script>

<nav>
	<a class="home text-link-fx" href="/">žižkárna</a>
	<!-- <button on:click={() => showMenu(!menuShown)}>
		<svg xmlns="http://www.w3.org/2000/svg" width="32" height="32" viewBox="0 0 16 16">
			{#if !menuShown}
				<path
					transition:fade
					fill-rule="evenodd"
					d="M2.5 12a.5.5 0 0 1 .5-.5h10a.5.5 0 0 1 0 1H3a.5.5 0 0 1-.5-.5m0-4a.5.5 0 0 1 .5-.5h10a.5.5 0 0 1 0 1H3a.5.5 0 0 1-.5-.5m0-4a.5.5 0 0 1 .5-.5h10a.5.5 0 0 1 0 1H3a.5.5 0 0 1-.5-.5"
				/>
			{:else}
				<path
					transition:fade
					d="M2.146 2.854a.5.5 0 1 1 .708-.708L8 7.293l5.146-5.147a.5.5 0 0 1 .708.708L8.707 8l5.147 5.146a.5.5 0 0 1-.708.708L8 8.707l-5.146 5.147a.5.5 0 0 1-.708-.708L7.293 8z"
				/>
			{/if}
		</svg>
	</button> -->
	<div class="wide-nav">
		<a class="text-link-fx" class:active={$page.url.pathname === '/about'} href="/#about"
			>{langs[$lang].menu[0]}</a
		>
		<a
			class="text-link-fx"
			class:active={$page.url.pathname === '/programme'}
			href="https://program.zizkarna.cz/"
			target="_blank">{langs[$lang].menu[1]}</a
		>
		<a class="text-link-fx" class:active={$page.url.pathname === '/venues'} href="/venues"
			>{langs[$lang].menu[2]}</a
		>
		<a class="text-link-fx" class:active={$page.url.pathname === '/markets'} href="/markets"
			>{langs[$lang].menu[3]}</a
		>
		<!-- TODO hvr clr -->
		<a class="text-link-fx" class:active={$page.url.pathname === '/zlab'} href="/zlab"
			>{langs[$lang].menu[4]}</a
		>
		<a class="text-link-fx" class:active={$page.url.pathname === '/contacts'} href="/contacts"
			>{langs[$lang].menu[5]}</a
		>
		<button class="text-link-fx" on:click={() => lang.set($lang === 'cs' ? 'en' : 'cs')}
			>{$lang === 'cs' ? 'en' : 'cs'}</button
		>
	</div>
</nav>

<!-- {#if menuShown}
	<div class="small-nav-bg" transition:blur>
		<div class="small-nav">
			<a on:click={() => showMenu(false)} href="/reference">Reference</a>
			<a on:click={() => showMenu(false)} href="/graficke-studio-brno">Studio</a>
			<a on:click={() => showMenu(false)} href="/kontakt">Kontakt</a>
		</div>
	</div>
{/if} -->

<style>
	nav {
		position: fixed;
		width: calc(100% - 2 * var(--base-px));
		top: 0;
		left: 0;

		display: flex;
		justify-content: space-between;
		align-items: center;

		z-index: 100;

		background-color: var(--white);
		border-bottom: 2px solid var(--black);

		padding: calc(var(--base-px) / 2) var(--base-px);
	}

	nav .wide-nav a {
		margin: 0 1em;
	}
	nav .wide-nav a:first-of-type {
		margin-left: 0;
	}

	nav button {
		all: unset;
		margin-left: 1em;
		cursor: pointer;
		transition: all .2s ease-in-out;
	}

	.small-nav-bg {
		position: fixed;
		width: 100%;
		height: 100%;

		top: 0;
		left: 0;

		z-index: 90;
		background-color: white;
	}

	.small-nav {
		padding-left: var(--general-px);

		display: flex;
		flex-direction: column;

		margin-top: 25%;
		height: 100%;
	}

	.small-nav a {
		padding-top: calc(var(--general-px) * 2);
		font-size: 40px;
	}

	@media screen and (max-width: 900px) {
		nav {
			padding: calc(var(--general-px) / 2) 0;
		}

		nav .wide-nav {
			display: none;
		}

		nav button {
			display: inline-flex;
		}
	}
</style>
