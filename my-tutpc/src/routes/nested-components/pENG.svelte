<script lang="ts">
	import { onMount } from "svelte";
	import { createEventDispatcher } from "svelte";

	const dispatch = createEventDispatcher();

	export let point: number[];
	let totalPoints = 0;
	let gift = "";

	$: calculateTotalPoints();
	$: determineGift();

	function calculateTotalPoints() {
		totalPoints = point.reduce((acc, curr) => acc + curr, 0);
	}
	function determineGift() {
		if (totalPoints >= 10 && totalPoints <= 13) {
			gift = "BAS";
		} else if (totalPoints >= 14 && totalPoints <= 16) {
			gift = "CITU";
		} else if (totalPoints >= 17 && totalPoints <= 19) {
			gift = "LLB";
		} else if (totalPoints >= 20 && totalPoints <= 22) {
			gift = "BIR";
		} else if (totalPoints >= 23 && totalPoints <= 25) {
			gift = "PBIC";
		} else if (totalPoints >= 26 && totalPoints <= 28) {
			gift = "SPD";
		} else if (totalPoints >= 29 && totalPoints <= 31) {
			gift = "TBS";
		} else if (totalPoints >= 32 && totalPoints <= 34) {
			gift = "BJM";
		} else if (totalPoints >= 35 && totalPoints <= 37) {
			gift = "BE";
		} else if (totalPoints >= 38 && totalPoints <= 40) {
			gift = "PPE";
		}
	}

	function reset() {
		window.location.reload();
	}

	function downloadImage(gift: string) {
		const link = document.createElement('a');
		link.href = `./src/public/Img/GO/${gift}.png`;
		link.download = `gift.png`;
		document.body.appendChild(link);
		link.click();
		document.body.removeChild(link);
	}

	onMount(() => {
	});

</script>

<div class="container">

	<img src={`./src/public/Img/GO/${gift}.png`} alt="{gift}" />

	<div class="controls">
		<button on:click={reset}>ReStart Game</button>
		<button on:click={() => downloadImage(gift)}>Download Image</button>
	</div>

</div>

<style>

	@font-face {
		font-family: 'CloudLoop';
		src: url('./font/CloudLoop-Regular.otf') format('opentype');
		font-weight: normal;
		font-style: normal;
		font-display: swap;
	}
	.container {
		display: grid;
		grid-template-rows: 90% 10%;
		align-items: center;
		justify-items: center;
		height: 100%;
		width: auto;
		object-fit: contain;
	}

	img {
		max-width: 100%;
		height: auto;
	}

	.controls {
		display: grid;
		grid-template-columns: 1fr 1fr;
		align-items: center;
		justify-content: center;
		width: 100%;
		height: 100%;
		padding-top: 5%;
	}

	button {
		font-family: 'CloudLoop';
		font-size: 16px;
		min-width: 60%;
		padding: 5px;
		padding-left: 10%;
		padding-right: 10%;
		color: black;
		border: 1px solid black;
		border-radius: 20px;
		background-color: white;
		transition: background-color 0.3s;
		align-self: center;
		justify-self: center;
	}
</style>
