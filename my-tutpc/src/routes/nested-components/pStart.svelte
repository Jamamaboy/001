<script>
	import { createEventDispatcher } from "svelte";
	export let page;
	export let point;
	export let imgWidth;
	export let imgHeight;
	export let contentHeight;

	const dispatch = createEventDispatcher();

	function handleClick() {
		dispatch('nextPage');
	}


</script>

<div class="content" style="height: {contentHeight}px;">
	<div class="space"></div>
	<button on:click={handleClick}>Start</button>
</div>

<style>
	.content {
		display: grid;
		z-index: 1;
		grid-template-columns: 1fr;
		grid-template-rows: 20fr 1fr;
	}
	.space {
		height: 100%;
	}
</style>
