<script lang="ts">
	import StartView from '$lib/startView.svelte';
	import FlashcardView from '$lib/flashcardView.svelte'; // placeholder, you'll build this

	let currentView = 'start';

	function goToQuiz() {
		currentView = 'quiz';
	}
</script>

{#if currentView === 'start'}
	<StartView onStart={goToQuiz} />
{:else if currentView === 'quiz'}
	<FlashcardView />
{/if}
