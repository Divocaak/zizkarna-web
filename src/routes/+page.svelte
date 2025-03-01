<script>
	import ContactShort from '$lib/ContactShort.svelte';
	import ContentBlock from '$lib/ContentBlock.svelte';
	import ImageBlock from '$lib/ImageBlock.svelte';
	import StyledButton from '$lib/StyledButton.svelte';

	import { lang } from '$lib/stores/LangStore.js';
	import langs from '$lib/localization.json';
</script>

<ImageBlock src="/imgs/7.jpg">
	<svg
		class="logo"
		xmlns="http://www.w3.org/2000/svg"
		viewBox="0 0 52.39 159.74"
		fill="var(--white)"
	>
		<filter id="dropshadow" height="200%" width="200%">
			<feGaussianBlur in="SourceAlpha" stdDeviation="2" />
			<feOffset dx="1" dy="1" result="offsetblur" />
			<feComponentTransfer>
				<feFuncA type="linear" slope=".5" />
			</feComponentTransfer>
			<feMerge>
				<feMergeNode />
				<feMergeNode in="SourceGraphic" />
			</feMerge>
		</filter>
		<polygon
			points="0.31 22.34 0.31 29.65 48.98 29.65 0.31 80.78 0.31 94.69 49.02 94.69 0.31 145.86 0.31 159.74 52.08 159.74 52.08 152.43 2.88 152.43 52.08 101.18 52.08 87.39 2.85 87.39 52.08 36.1 52.08 22.34 0.31 22.34"
			style="filter:url(#dropshadow)"
		/>
		<rect width="52.39" height="6.67" style="filter:url(#dropshadow)" />
	</svg>
	<p class="catch-phrase">{langs[$lang].index.landing}</p>
</ImageBlock>
<span id="about"></span>
<ContentBlock src="/imgs/5.jpg" imgsLeft={true}>
	<h1>{langs[$lang].index.about.heading}</h1>
	<p id="about">{langs[$lang].index.about.about}</p>
	<StyledButton href="/about" label={langs[$lang].index.about.btn} />
</ContentBlock>
<ImageBlock src="/imgs/20.jpg">
	<a
		href="https://program.zizkarna.cz/"
		target="_blank"
		class="text-link-fx inverted"
		id="program-btn">{langs[$lang].index.btn}</a
	>
</ImageBlock>
<div class="contact-panel">
	<div class="default-content-block">
		<h1>{langs[$lang].index.contact.whereToFindUs}</h1>
		<p>Žižkova tř. 28, České Budějovice</p>
		<iframe
			src="https://www.google.com/maps/embed?pb=!1m18!1m12!1m3!1d2915.705759358011!2d14.48279907659605!3d48.97214539269423!2m3!1f0!2f0!3f0!3m2!1i1024!2i768!4f13.1!3m3!1m2!1s0x47734f8fb6d689ab%3A0x30873f0fb4b41a4c!2zxb1pxb5rw6FybmE!5e1!3m2!1scs!2scz!4v1740487550291!5m2!1scs!2scz"
			title="map"
			width="100%"
			height="100%"
			style="border:0;"
			allowfullscreen=""
			loading="lazy"
			referrerpolicy="no-referrer-when-downgrade"
		></iframe>
	</div>
	<div class="default-content-block">
		<h1>{langs[$lang].index.contact.howToConnect}</h1>
		<ContactShort label={langs[$lang].index.contact.general} mail="info@zizkarna.cz" />
		<ContactShort label={langs[$lang].index.contact.media} mail="media@zizkarna.cz" />
		<ContactShort label={langs[$lang].index.contact.markets} mail="trhy@zizkarna.cz" />
		<ContactShort label={langs[$lang].index.contact.musical} mail="hudebni@zizkarna.cz" />
		<StyledButton href="/contacts" label={langs[$lang].index.contact.btn} />
	</div>
</div>

<style>
	svg.logo {
		height: 30%;
	}

	.catch-phrase {
		color: var(--white);

		font-weight: 300;
		font-size: var(--fs-16);
		line-height: 18px;

		max-width: 150px;
		text-shadow: 2px 3px 3px black;
		text-align: center;
	}

	.contact-panel {
		position: relative;
		width: 100vw;
		height: 100vh;
		padding: 0 !important;
		margin: 0 !important;

		display: grid;
		grid-template-columns: repeat(2, 1fr);

		font-weight: 300;
		font-size: var(--fs-32);
		line-height: 48px;
	}

	h1 {
		font-weight: 800;
		font-size: var(--fs-72);
		line-height: 85px;
	}

	#about {
		font-weight: 300;
		font-size: var(--fs-24);
		line-height: 31px;
	}

	#program-btn {
		font-weight: 800;
		font-size: var(--fs-48);
		line-height: 48px;
		text-transform: uppercase;

		transition: all 0.45s;
	}

	#program-btn:hover {
		text-shadow: 0px 0px 5px var(--primary);
	}
</style>
