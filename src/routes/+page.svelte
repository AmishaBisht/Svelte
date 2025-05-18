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
