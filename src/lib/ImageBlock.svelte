<script>
	export let src;
</script>

<div style="background-image: url('{src}');">
	<slot></slot>
</div>

<style>
	div {
		position: relative;
		width: 100vw;
		height: 100vh;
		padding: 0 !important;
		margin: 0 !important;

		background-position: center;
		background-size: cover;

		align-items: center;
		justify-content: center;
		display: flex;
        flex-direction: column;
	}
</style>
