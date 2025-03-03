<script>
	export let label;
	export let mail;
</script>

<div>
	<b>{label}</b><br />
	<a href="mailto:{mail}" class="text-link-fx">{mail}</a>
</div>

<style>
    div{
        position: relative;
        width: 100%;
    }
</style>