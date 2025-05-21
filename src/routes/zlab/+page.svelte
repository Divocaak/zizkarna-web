<script>
	import { lang } from '$lib/stores/LangStore.js';
	import langs from '$lib/localization.json';
	import ImageBlock from '$lib/ImageBlock.svelte';
	import ContentBlock from '$lib/ContentBlock.svelte';
	import StyledButton from '$lib/StyledButton.svelte';
</script>

<svelte:head>
	<script type="application/ld+json">
		{
			"@context": "https://schema.org",
			"@type": "EducationalOrganization",
			"name": "Žižkárenská Kulturní Laboratoř",
			"alternateName": "Ž.lab",
			"url": "https://zizkarna.cz/zlab",
			"description": "Experimentální platforma pro mladé lidi, kteří si chtějí osvojit nebo zlepšit své znalosti a dovednosti v kreativních odvětvích.",
			"parentOrganization": {
				"@type": "Organization",
				"name": "Žižkárna",
				"url": "https://zizkarna.cz"
			},
			"location": {
				"@type": "Place",
				"name": "Žižkárna",
				"address": {
					"@type": "PostalAddress",
					"streetAddress": "Žižkova tř. 28",
					"addressLocality": "České Budějovice",
					"postalCode": "370 01",
					"addressCountry": "CZ"
				}
			}
		}
	</script>
</svelte:head>

<div class="wrapper">
	<div class="panel">
		<svg xmlns="http://www.w3.org/2000/svg" viewBox="0 0 262.78 94.24">
			<rect x="9.86" y="55.03" width="7.18" height="23.69" />
			<rect x="82.66" y="55.03" width="7.18" height="23.69" />
			<rect x="242.98" y="55.18" width="7.18" height="23.69" />
			<rect
				x="46.26"
				y="49.51"
				width="7.18"
				height="65.62"
				transform="translate(132.17 32.46) rotate(90)"
			/>
			<rect
				x="162.82"
				y="5.75"
				width="7.18"
				height="153.13"
				transform="translate(248.73 -84.1) rotate(90)"
			/>
			<path
				d="M31.8,60.22l31.45-22.46h-31.45v-5.4h33.88v10.95l-31.45,22.38h31.45v5.56H31.8v-11.03ZM39.7,13.12l9.08,7.36,9-7.36,3.99,3.84-12.99,10.4-13.07-10.4,3.99-3.84Z"
			/>
			<g>
				<path
					d="M107.61,65.35h10.75V20.27h-8.04v-5.87h10.9c2.55,0,4.02,1.31,4.02,3.87v47.09h10.75v5.88h-28.38v-5.88Z"
				/>
				<path
					d="M154.72,49.35l15.08-1.47c-.31-6.96-3.4-10.28-10.36-10.28-5.34,0-9.28,2.47-9.9,8.89h-6.81c.85-8.74,6.81-14.46,16.86-14.46,11.13,0,17.09,6.88,17.09,17.24v16.08h5.64v5.88h-7.04c-2.94,0-4.64-1.7-4.64-4.64v-4.87c-1.78,5.41-6.26,10.28-15.77,10.28-11.29,0-12.99-7.42-12.99-11.45,0-6.11,3.71-10.36,12.84-11.21ZM155.95,66.36c8.35,0,13.84-5.88,13.84-13.61l-13.92,1.47c-4.72.47-7.19,1.78-7.19,5.49,0,4.41,2.86,6.65,7.27,6.65Z"
				/>
				<path
					d="M189.54,14.4h6.88v27.68c2.55-5.8,7.96-10.05,16.47-10.05,11.06,0,18.02,8.27,18.02,19.95s-6.96,20.03-18.02,20.03c-8.27,0-13.76-4.1-16.47-10.21v9.43h-6.88V14.4ZM210.65,66.12c7.5,0,13.45-4.49,13.45-14.15s-5.96-14.07-13.45-14.07-14.07,4.72-14.07,14.07,6.57,14.15,14.07,14.15Z"
				/>
			</g>
		</svg>
	</div>
	<div class="panel default-content-block">
		<h1>{langs[$lang].zlab.heading}</h1>
		{#each langs[$lang].zlab.texts as text}
			<p>{text}</p>
		{/each}
		<div class="warning">
			<svg xmlns="http://www.w3.org/2000/svg" viewBox="0 0 315.29 368.48">
				<path
					d="M148.71,41.2L20.97,319.07c-2.99,6.51,1.76,13.94,8.93,13.94h255.48c7.17,0,11.93-7.43,8.93-13.94L166.58,41.2c-3.51-7.63-14.36-7.63-17.87,0Z"
					fill="var(--zlab-primary)"
				/>
				<g>
					<circle cx="156" cy="288.39" r="13.95" />
					<path
						d="M161.74,256.27l28.2-119.02c.43-1.82-.95-3.56-2.82-3.56h-62.23c-2.01,0-3.28,1.6-2.82,3.56l28.2,119.02c1.43,6.04,10.03,6.04,11.46,0Z"
					/>
				</g>
			</svg>
			<p>
				{langs[$lang].zlab.warning}
			</p>
		</div>
		<a
			href="https://docs.google.com/forms/d/e/1FAIpQLSdRPxeWKcGwU5bPg8fUtF99RaMQb3cc5IaCKbo9XbiZFNrrHA/viewform"
			target="_blank">{langs[$lang].zlab.soundBtn}</a
		>
		<a
			href="https://docs.google.com/forms/d/e/1FAIpQLSdI8ntWVbH0GcU9wyjrltMIhvd8k2VvZO5toh1_BaL3ger9LA/viewform"
			target="_blank">{langs[$lang].zlab.lightsBtn}</a
		>
	</div>
</div>

<style>
	:root {
		--border-w: 10px;
	}

	.wrapper {
		position: relative;
		width: 100vw;
		height: 100vh;
		padding: 0 !important;
		margin: 0 !important;

		display: grid;
		grid-template-columns: repeat(2, 1fr);
	}

	.panel:first-of-type {
		background-color: var(--zlab-primary);
		padding: 5rem;
		align-content: center;
	}

	h1 {
		color: var(--zlab-primary);
		font-weight: 800;
		font-size: var(--fs-48);
		line-height: 48px;
	}

	p,
	a {
		font-weight: 300;
		font-size: var(--fs-32);
		line-height: 35px;
		margin: 0;
	}

	.warning {
		display: grid;
		grid-template-columns: 1fr 4fr;
		justify-content: center;
		align-items: center;
		gap: 1rem;
	}

	.warning p {
		font-weight: 400;
	}

	a {
		position: relative;
		width: 100%;
		padding: 1rem;

		box-shadow:
			calc(var(--border-w) * -1) 0 0 0 var(--black),
			var(--border-w) 0 0 0 var(--black),
			0 calc(var(--border-w) * -1) 0 0 var(--black),
			0 var(--border-w) 0 0 var(--black);
		color: var(--black);

		text-align: center;
		text-decoration: none;
		text-transform: uppercase;
		font-weight: 800;

		transition: all 0.25s;
	}

	a:hover {
		box-shadow:
			calc(var(--border-w) * -1) 0 0 0 var(--zlab-primary),
			var(--border-w) 0 0 0 var(--zlab-primary),
			0 calc(var(--border-w) * -1) 0 0 var(--zlab-primary),
			0 var(--border-w) 0 0 var(--zlab-primary);
		color: var(--zlab-primary);
	}

	@media (max-width: 575px) {
		.wrapper {
			grid-template-rows: repeat(2, 1fr);
			grid-template-columns: none;
		}

		a {
			width: max-content;
		}
	}
</style>
