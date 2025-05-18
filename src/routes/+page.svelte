<script>
	import Component from '$lib/Component.svelte';
	let count = $state(0);

	function increase_counter() {
		count += 1;
	}
</script>

<Component name="Hello from Svelte" />
<button onclick={increase_counter}>
	{#if count < 2}
		<p>Clicked {count} time</p>
	{:else}
		<p>Clicked {count} times</p>
	{/if}
</button>

<style>
	button {
		background-color: #008cba;
		color: white;
		padding: 4px 8px;
		border: none;
		margin: 4px 2px;
		cursor: pointer;
		font-size: 12px;
		border-radius: 4px;
	}

	button:hover {
		background-color: #45a049;
	}
</style>
