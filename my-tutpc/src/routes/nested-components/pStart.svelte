<script>
	import { createEventDispatcher } from "svelte";
	export let contentHeight;
	export let contentWidth;

	const dispatch = createEventDispatcher();
	/**
     * @param {number | undefined} [additionalPoint]
     * @param {number} [pageIncrement]
     */
	 function handleClick(additionalPoint, pageIncrement) {
		dispatch('nextPage', { additionalPoint, pageIncrement });
	}



</script>

<div class="content" style="height: {contentHeight}px; width: {contentWidth}px;">
	<div class="space"></div>
	<button on:click={() => handleClick(0, 1)}>Start</button>
</div>

<style>
	@font-face {
		font-family: 'CloudLoop';
		src: url('./font/CloudLoop-Regular.otf') format('opentype');
		font-weight: normal;
		font-style: normal;
	}
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
