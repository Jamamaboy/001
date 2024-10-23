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
	<button on:click={() => handleClick(0, 1)}></button>
</div>

<style>
	@font-face {
		font-family: 'CloudLoop';
		src: url('./font/CloudLoop-Regular.otf') format('opentype');
		font-weight: normal;
		font-style: normal;
		font-display: swap;
	}
	.content {
		display: grid;
		z-index: 1;
		justify-items: center;
		align-items: center;
	}

	button {
		font-size: 1px;
		width: 100%;
		height: 100%;
		background: none;
		border: none;
		object-fit: contain;
	}
</style>
