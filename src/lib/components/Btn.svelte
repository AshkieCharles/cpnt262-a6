<script>
	import { createEventDispatcher } from 'svelte';

	const dispatch = createEventDispatcher();

	export let text;

	// Everytime the user clicks the button, the previous/next player is activated inside the players component
	function defaultFn() {
		dispatch('toggle', {});
	}
</script>

<button on:click={defaultFn}> {text} </button>