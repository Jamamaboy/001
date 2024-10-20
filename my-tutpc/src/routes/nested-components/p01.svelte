<script>
	import { createEventDispatcher } from "svelte";
	export let page;
	export let point;
	export let imgWidth;
	export let imgHeight;

	const dispatch = createEventDispatcher();

	function handleClick() {
		dispatch('nextPage');
	}
</script>
		<div class="space"></div>
		<button on:click={handleClick}>Start</button>
<style>
</style>
