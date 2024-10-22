<script>
	let page = 1;
	let point = [0];
	let contentHeight = 0;
	let contentWidth = 0;

	let history = [1];

	import PStart from './nested-components/pStart.svelte';
	import Ptbc from './nested-components/ptbc.svelte';
	import Pn from './nested-components/pn.svelte';
	import Ps from './nested-components/ps.svelte';
	import Pl from './nested-components/pl.svelte';
	import PEng from './nested-components/pENG.svelte';

	const page_Start = [1];
	const page_tbc = [2,3,7,8,13,14,16,17,18,20,22,24,26,31,34,36,37,38];
	const page_nextX2 = [4,5];
	const page_nextX3 = [9,10,11];
	const page_n = [6,12];
	const page_s = [15];
	const page_l = [19,21,23,25,27,28,29,30,32,33,35];
	const page_nextP = [39];
	const page_ENG = [40];

	/**
	 * @param {{ target: any; }} event
	 */
	function handleImageLoad(event) {
		const img = event.target;
		contentHeight = img.offsetHeight;
		contentWidth = img.offsetWidth;
	}

	/**
	 * @param {{ detail: { additionalPoint: number; pageIncrement: number; }} } event
	 */
	 function handleNextPage(event) {
		const { additionalPoint, pageIncrement } = event.detail

		if (additionalPoint > 0) {
			point.push(additionalPoint);
		}

		let nextPage;
		switch (page) {
			case 7:
				nextPage = 9;
				break;
			case 13:
				nextPage = 15;
				break;
			case 36:
				nextPage = 38;
				break;
			default:
				nextPage = page + pageIncrement;
		}
		history.push(page);
		page = nextPage;

		console.log("Points:", point);
		console.log("Page:", page);
		console.log("History:", history);
	}

	function handlePreviousPage() {
		if (history.length > 0) {
			const previousPage = history.pop();
			if (previousPage !== undefined) {
				page = previousPage;
				console.log('Page decreased to:', page);
			}
		} else {
			console.log('No previous pages in history.');
		}
	}


</script>

<body>

	<img src="./src/public/Img/{page}.png" alt="P{page}" on:load={handleImageLoad}>

    <!-- Start [1]-->
	{#if page_Start.includes(page)}
		<PStart contentHeight={contentHeight} contentWidth={contentWidth} on:nextPage={handleNextPage}/>

	{/if}

	<!-- TBC [2,3,7,8,13,14,16,17,18,20,24,26,31,34,36,37,38]--><!-- NextX2 [4,5]--><!-- NextX3 [9,10,11]-->
	{#if page_tbc.includes(page) || page_nextX2.includes(page) || page_nextX3.includes(page)}
		<Ptbc contentHeight={contentHeight} contentWidth={contentWidth} on:nextPage={handleNextPage} on:previousPage={handlePreviousPage}/>
	{/if}

	{#if page_nextX2.includes(page)}
	<!-- NextX2 [4,5]-->

	{/if}

	{#if page_nextX3.includes(page)}
	<!-- NextX3 [9,10,11]-->
	{/if}

	<!-- N [6,12]-->
	{#if page_n.includes(page)}
		<Pn contentHeight={contentHeight} contentWidth={contentWidth} page={page} on:nextPage={handleNextPage}/>
	{/if}

	<!-- S [15]-->
	{#if page_s.includes(page)}
		<Ps contentHeight={contentHeight} contentWidth={contentWidth} page={page} on:nextPage={handleNextPage}/>
	{/if}

	<!-- L [19,21,23,25,26,27,28,29,30,32,33,35]-->
	{#if page_l.includes(page)}
		<Pl contentHeight={contentHeight} contentWidth={contentWidth} page={page} on:nextPage={handleNextPage}/>
	{/if}

	{#if page_nextP.includes(page)}
	<!-- NestP [39]-->
	{/if}

	{#if page_ENG.includes(page)}
		<PEng />
	{/if}

</body>

<style>

@font-face {
		font-family: 'CloudLoop';
		src: url('./font/CloudLoop-Regular.otf') format('opentype');
		font-weight: normal;
		font-style: normal;
	}
body {
	display: flex;
	justify-content: center;
	align-items: center;
	min-height: 100vh;
	margin: 0;
}

img {
	position: absolute;
	z-index: 0;
	max-width: 100vw;
	max-height: 100vh;
	width: auto;
	height: auto;
	object-fit: contain;
}
</style>
