<script>
	import ImageBlock from '$lib/ImageBlock.svelte';
	import { lang } from '$lib/stores/LangStore.js';
	import langs from '$lib/localization.json';
	import ContactBlock from '$lib/ContactBlock.svelte';
	import ContentBlock from '$lib/ContentBlock.svelte';
</script>

<!-- https://yqnn.github.io/svg-path-editor/ -->
<svg class="clip-path-svg">
	<clipPath id="img-top-clip-path" clipPathUnits="objectBoundingBox">
		<path d="m0 0h1v.527l-.365.47h-.635"></path>
	</clipPath>
	<clipPath id="img-bottom-clip-path" clipPathUnits="objectBoundingBox">
		<path d="m.366.0h.634v.995h-.858c-.027-.182-.057-.305-.137-.509z"></path>
	</clipPath>
	<clipPath id="theatre-clip-path" clipPathUnits="objectBoundingBox">
		<path d="m0 0h.5715c.075.582-.085.414-.59.429"></path>
	</clipPath>
</svg>

<ImageBlock src="/imgs/9.jpg">
	<img id="logo" src="/markets_logo.png" alt="markets logo" />
</ImageBlock>
<ContentBlock src="/imgs/21.jpg">
	<p id="landing">{langs[$lang].market.landing}</p>
	<p id="time">9:00</p>
	<a href="https://program.zizkarna.cz/">{langs[$lang].market.btn}</a>
</ContentBlock>
<div class="designed">
	<div id="two-images-block">
		<img src="/imgs/10.jpg" alt="fresh pastry" />
		<img src="/imgs/4.jpg" alt="the best coffee" />
		<p>{langs[$lang].market.notOnly}</p>
		<p>{langs[$lang].market.brunch} <span>brunch!</span></p>
	</div>
	<ImageBlock src="/imgs/14.jpg">
		<div id="theatre">
			<p>{langs[$lang].market.theatre}</p>
		</div>
	</ImageBlock>
</div>

<style>
	.clip-path-svg {
		position: absolute;
		z-index: 1;
	}

	#logo {
		position: relative;
		width: 50%;
		height: auto;
		filter: invert() drop-shadow(0px 0px 5px black);
	}

	#landing {
		font-weight: 800;
		font-size: var(--fs-72);
		line-height: 82px;

		margin: 0;
	}

	#time {
		color: var(--primary);
		font-weight: 800;
		font-size: var(--fs-150);
		line-height: 100px;
		text-align: end;

		width: 100%;
		margin: 0;
	}

	a {
		width: 100%;

		font-weight: 300;
		font-size: var(--fs-72);
		line-height: 90px;
		text-align: center;

		color: var(--black);
		text-decoration: none;

		border: 5px solid var(--black);
		border-radius: 50px;

		transition: all 0.25s ease-in-out;
	}

	a:hover {
		background-color: var(--primary);
	}

	#two-images-block {
		position: relative;
		width: 100%;
		min-height: 100vh;
	}

	#two-images-block img {
		position: absolute;
		width: 50%;
		height: auto;
	}

	#two-images-block img:first-of-type {
		clip-path: url(#img-top-clip-path);
	}

	#two-images-block img:last-of-type {
		bottom: 0;
		right: 0;
		clip-path: url(#img-bottom-clip-path);
	}

	#two-images-block p {
		position: absolute;

		font-weight: 300;
		font-size: var(--fs-72);
		line-height: 90px;
	}

	#two-images-block p:first-of-type {
		top: 0;
		left: 50%;
		max-width: calc(50% - var(--base-px));
		padding-left: var(--base-px);
	}

	#two-images-block p:last-of-type {
		top: calc(50% + var(--base-px));
		left: 0;
		max-width: calc(50% - var(--content-px));
		padding-left: var(--content-px);
	}

	#two-images-block p:last-of-type span {
		color: var(--primary);
		text-transform: uppercase;
		font-weight: 800;
	}

	#theatre {
		position: absolute;
		width: 100%;
		height: 100%;
		background-color: var(--white);

		clip-path: url(#theatre-clip-path);
	}

	#theatre p {
		font-weight: 800;
		font-size: var(--fs-48);
		line-height: 60px;
		max-width: 50%;
		padding-left: var(--content-px);
		padding-top: var(--base-px);
	}

	@media (max-width: 575px) {
		#logo {
			width: 100%;
		}

		.designed {
			display: none;
		}

		#landing {
			font-size: var(--fs-64);
			line-height: 70px;
			margin: 0;
		}

		#time {
			font-size: var(--fs-72);
			line-height: 80px;
			margin: 0;
		}

		a {
			font-size: var(--fs-64);
			line-height: 90px;

			border: 5px solid var(--black);
			border-radius: 50px;
		}
	}
</style>
