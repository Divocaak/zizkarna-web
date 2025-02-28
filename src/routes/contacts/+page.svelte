<script>
	import { lang } from '$lib/stores/LangStore.js';
	import langs from '$lib/localization.json';
	import ContentBlock from '$lib/ContentBlock.svelte';
	import ContactBlock from '$lib/ContactBlock.svelte';
	import StyledButton from '$lib/StyledButton.svelte';
</script>

<ContentBlock src="/imgs/15.jpg" leftPanelFr={3} contentPadding={0}>
	<div class="wrapper">
		<div class="panel contacts">
			<h1>{langs[$lang].contacts.contacts.heading}</h1>
			<div class="contact-list">
				<ContactBlock
					label={langs[$lang].contacts.contacts.music}
					mail="hudebni@zizkarna.cz"
					name="Vojtěch Divoký"
					mailSecondary="vojtech@zizkarna.cz"
				/>
				<ContactBlock
					label={langs[$lang].contacts.contacts.programme}
					mail="dramaturgie@zizkarna.cz"
					name="Petra Hadová"
					mailSecondary="petra@zizkarna.cz"
				/>
				<ContactBlock
					label={langs[$lang].contacts.contacts.media}
					mail="media@zizkarna.cz"
					name="Radek Matoušek"
					mailSecondary="radek@zizkarna.cz"
				/>
			</div>
			<div class="contact-list">
				<ContactBlock label={langs[$lang].contacts.contacts.markets} mail="trhy@zizkarna.cz" />
				<ContactBlock label="Ž.lab" mail="zlab@zizkarna.cz" />
				<ContactBlock label="Info" mail="info@zizkarna.cz" />
			</div>
		</div>
		<div class="panel">
			<h1 class="border-b">{langs[$lang].contacts.forPromoters.heading}</h1>
			<StyledButton label="Logo" href="" target="_blank" />
			<StyledButton
				label={langs[$lang].contacts.forPromoters.presentationBtn}
				href=""
				target="_blank"
			/>
			<h1 class="border-b">{langs[$lang].contacts.residency}</h1>
			<p class="border-b">
				Žižkárna z.s.<br />
				IČ: 26559234 (nejsme plátci DPH)<br />
				Česká 222/7, České Budějovice 37001
			</p>
			<h1>{langs[$lang].contacts.followUs}</h1>
			<StyledButton label="Instagram" href="https://instagram.com/zizkarna/" target="_blank" />
			<StyledButton label="Facebook" href="https://facebook.com/zizkarnacb" target="_blank" />
			<StyledButton label="YouTube" href="https://youtube.com/@Zizkarna" target="_blank" />
		</div>
		<div class="panel">
			<h1 class="border-b">{langs[$lang].contacts.address}</h1>
			<p>Žižkova tř. 28, České Budějovice</p>
			<iframe
				src="https://www.google.com/maps/embed?pb=!1m18!1m12!1m3!1d2915.705759358011!2d14.48279907659605!3d48.97214539269423!2m3!1f0!2f0!3f0!3m2!1i1024!2i768!4f13.1!3m3!1m2!1s0x47734f8fb6d689ab%3A0x30873f0fb4b41a4c!2zxb1pxb5rw6FybmE!5e1!3m2!1scs!2scz!4v1740487550291!5m2!1scs!2scz"
				title="map"
				width="100%"
				height="auto"
				style="border:0;"
				allowfullscreen=""
				loading="lazy"
				referrerpolicy="no-referrer-when-downgrade"
			></iframe>
		</div>
	</div>
</ContentBlock>

<style>
	.wrapper {
		position: relative;
		width: 100%;
		height: 100%;
		padding: 0 !important;
		margin: 0 !important;

		background-color: red;

		display: grid;
		grid-template-columns: 3fr 2fr;
	}

	.panel {
		background-color: blue;
		margin: var(--base-px);
	}

	.panel:first-of-type {
		grid-column: span 2;
	}

	.contacts {
		display: grid;
		grid-template-columns: 3fr 2fr;
	}

	.contact-list {
		background-color: green;
		width: 100%;
	}
	.contact-list:last-of-type {
		margin-left: var(--base-px);
	}

	.contacts h1 {
		grid-column: span 2;
	}

	.border-b {
		border-bottom: 2px solid var(--black);
	}
</style>
