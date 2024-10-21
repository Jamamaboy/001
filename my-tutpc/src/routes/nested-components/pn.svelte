<script>
	import { createEventDispatcher } from "svelte";
	export let page;
	export let contentHeight;
	export let contentWidth;

	const dispatch = createEventDispatcher();

	function handleClick() {
		dispatch('nextPage');
	}


</script>

<div class="content" style="height: {contentHeight}px; width: {contentWidth}px;">
	<div class="space"></div>
	{page}
	<button on:click={handleClick}>Start</button>
</div>

<style>
	.content {
		display: grid;
		z-index: 1;
		justify-items: center;
		align-items: center;
	}
	.space {
		height: 100%;
	}
</style>
