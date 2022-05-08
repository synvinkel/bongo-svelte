<script lang="ts">
	import Button from '$lib/Button.svelte';

	function demoClick() {
		alert('Clicked it!');
	}
</script>

<div class="wrapper">
	<Button size="small" on:click={demoClick}>Small</Button>

	<Button size="medium" on:click={demoClick}>medium</Button>

	<Button size="large" on:click={demoClick}>large</Button>

	<Button size="large" on:click={demoClick} disabled>Disabled</Button>

	<Button type="contained" on:click={demoClick}>Contained</Button>

	<Button type="outlined" on:click={demoClick}>Outlined</Button>

	<Button type="outlined" loading on:click={demoClick}>Loading</Button>

</div>

<style>
	.wrapper {
		display: flex;
		flex-direction: column;
		gap: 20px;

		padding: 40px;
	}
</style>
