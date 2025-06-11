<script lang="ts">
	export let onStart: () => void;

	function switch_view() {
		onStart();
	}
</script>


<h3>Welcome to the Flashcard Game</h3>
<h4>
	Test your knowledge with these flashcards. Flip the card to see the answer. Try to get them all
	right!
</h4>

<button on:click={switch_view}>Start Quiz</button>
