<script>
	import ContactShort from '$lib/ContactShort.svelte';
	import ContentBlock from '$lib/ContentBlock.svelte';
	import ImageBlock from '$lib/ImageBlock.svelte';
	import StyledButton from '$lib/StyledButton.svelte';
</script>

<ImageBlock src="/imgs/7.jpg">
	<!-- TODO shadows? -->
	<svg
		class="logo"
		xmlns="http://www.w3.org/2000/svg"
		viewBox="0 0 52.39 159.74"
		fill="var(--white)"
	>
		<polygon
			points="0.31 22.34 0.31 29.65 48.98 29.65 0.31 80.78 0.31 94.69 49.02 94.69 0.31 145.86 0.31 159.74 52.08 159.74 52.08 152.43 2.88 152.43 52.08 101.18 52.08 87.39 2.85 87.39 52.08 36.1 52.08 22.34 0.31 22.34"
		/>
		<rect width="52.39" height="6.67" />
	</svg>
	<p class="catch-phrase">Kulturní oáza<br />v centru<br />Českých Budějovic</p>
</ImageBlock>
<ContentBlock src="/imgs/5.jpg" imgsLeft={true}>
	<h1>O Žižkárně</h1>
	<p>
		Jsme kulturně-kreativní prostor v Českých Budějovicích pro všechny generace. Snažíme se oživit
		areál bývalých Žižkových kasáren a nabídnout občanům Českých Budějovic místo pro setkávání,
		zábavu a kreativitu. Jsme otevření všem umělcům a kreativcům.
	</p>
	<StyledButton href="about" label="Chci vědět víc!" />
</ContentBlock>
<ImageBlock src="/imgs/20.jpg">
	<a href="/programme" class="text-link-fx inverted">program</a>
</ImageBlock>
<div class="contact-panel">
	<div class="default-content-block">
		<h1>Kde nás najdete?</h1>
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
		<h1>Jak se s námi spojit?</h1>
		<ContactShort label="Obecné informace" mail="info@zizkarna.cz" />
		<ContactShort label="Média" mail="media@zizkarna.cz" />
		<ContactShort label="Trhy" mail="trhy@zizkarna.cz" />
		<ContactShort label="Hudební dramaturgie" mail="hudebni@zizkarna.cz" />
		<StyledButton href="contact" label="Více kontaktů a informace pro promotéry" />
	</div>
</div>

<style>
	svg.logo {
		height: 30%;
	}

	.catch-phrase {
		color: var(--white);
	}

	.contact-panel {
		position: relative;
		width: 100vw;
		height: 100vh;
		padding: 0 !important;
		margin: 0 !important;

		display: grid;
		grid-template-columns: repeat(2, 1fr);
	}
</style>
