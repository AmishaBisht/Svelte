<script lang="ts">
	let current_index = 0;
	let is_flipped = false;

	function goToNextCard() {
		is_flipped = false;
		current_index += 1;
	}

	const flashcards = [
		{
			question: 'What did the photon say when asked if it needed a suitcase?',
			answer: 'No thanks, I’m traveling light.'
		},
		{ question: "Why can't you trust atoms?", answer: 'Because they make up everything!' },
		{ question: 'What is Eleven’s favorite snack in *Stranger Things*?', answer: 'Eggo waffles.' },
		{
			question: 'Why did Iron Man never get a parking ticket?',
			answer: 'Because he always had a *Stark* reminder.'
		},
		{ question: "What's faster than light?", answer: 'Gossip at a high school cafeteria.' }
	];
</script>

{#if current_index < flashcards.length}
	<div>
		<p>{is_flipped ? flashcards[current_index].answer : flashcards[current_index].question}</p>
		<button on:click={() => (is_flipped = !is_flipped)}>
			{is_flipped ? 'Show Question' : 'Show Answer'}
		</button>
		{#if is_flipped}
			<button on:click={goToNextCard}>Next</button>
		{/if}
	</div>
{:else}
	<p>You've completed all flashcards!</p>
	<button
		on:click={() => {
			current_index = 0;
			is_flipped = false;
		}}
	>
		Start Again
	</button>
{/if}
