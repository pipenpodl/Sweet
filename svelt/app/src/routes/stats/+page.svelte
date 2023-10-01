<svelte:head>
	<title>About</title>
	<meta name="description" content="About this app" />
</svelte:head>

<script>
	import FormNameTable from "./FormNameTable.svelte";
	import ContentTable from "./ContentTable.svelte";
</script>

<div class="form_and_data">
	<FormNameTable></FormNameTable>
	<ContentTable></ContentTable>
</div>


<style>
	.form_and_data {
		display: grid;
	}
	
</style>