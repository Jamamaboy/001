<script lang="ts">
	import { createEventDispatcher } from "svelte";
	import { supabase } from '../../lib/supabase.js';

	export let contentHeight: number;
	export let contentWidth: number;
	export let points: number[];

	const dispatch = createEventDispatcher();

	let showButton = false;

	function showButtonAfterDelay() {
		setTimeout(() => {
			showButton = true;
		}, 2500);
	}

	showButtonAfterDelay();

	async function saveData(points: number[]) {
		const { data, error } = await supabase
			.from('points_pages')
			.insert([
				{ points: points },
			]);
		if (error) {
			console.error('Error inserting data:', error.message);
		} else {
			// console.log('Data inserted:', data);
		}
	}


	/**
     * @param {number} [pageIncrement]
     */
	function handleClick(pageIncrement: number) {
		saveData(points);
		dispatch('nextPage', {pageIncrement});
	}

</script>

<div class="content" style="height: {contentHeight}px; width: {contentWidth}px;">
	<div class="space"></div>
	{#if showButton}
		<button on:click={() => handleClick(1)}>Hope it shines bright for you! 💎✨</button>
	{/if}
	<div class="space"></div>
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
		grid-template-rows: 65% 45% 10%;
		width: 100%;
	}
	button {
		font-family: 'CloudLoop';
		border: 5em;
		cursor: pointer;
		outline: none;
		font-size: 13px;
		-webkit-transform: translate(0);
		transform: translate(0);
		background-image: linear-gradient(45deg, #4568dc, #b06ab3);
		padding: 0.7em 1em;
		box-shadow: 1px 1px 10px rgba(255, 255, 255, 0.438);
		-webkit-transition: box-shadow 0.25s;
		transition: box-shadow 0.25s;
		color: white;
		border-radius: 20px;
	}
	.space {
		height: 100%;
	}
</style>
