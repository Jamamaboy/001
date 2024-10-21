<script>
	let page = 1;
	let point = 0;
	let contentHeight = 0;
	let contentWidth = 0;

	import PStart from './nested-components/pStart.svelte';
	import Ptbc from './nested-components/ptbc.svelte';
	import Pn from './nested-components/pn.svelte';

	const page_Start = [1];
	const page_tbc = [2,3,7,8,13,14,16,17,18,20,24,26,31,34,36,37];
	const page_nextX2 = [4,5];
	const page_nextX3 = [9,10,11];
	const page_n = [6,12];
	const page_s = [15];
	const page_l = [19,21,23,25,26,27,28,29,30,32,33,35];
	const page_nextP = [38, 39];
	const page_ENG = [40];

	/**
	 * @param {{ target: any; }} event
	 */
	function handleImageLoad(event) {
		const img = event.target;
		contentHeight = img.offsetHeight;
		contentWidth = img.offsetWidth;
	}

	function handleNextPage() {
		page += 1;
		console.log(page);
	}

	function handlePreviousPage() {
		if (page > 0) {
			page -= 1;
			console.log('Page decreased to:', page);
		} else {
			console.log('Page is already at the minimum value.');
		}
	}

</script>

<body>

	<img src="./Img/{page}.png" alt="P{page}" on:load={handleImageLoad}>

	{#if page_Start.includes(page)}
    <!-- Start [1]-->
		<PStart contentHeight={contentHeight} contentWidth={contentWidth} on:nextPage={handleNextPage}/>

	{/if}

	{#if page_tbc.includes(page) || page_nextX2.includes(page) || page_nextX3.includes(page)}
	<!-- TBC [2,3,7,8,13,14,16,17,18,20,24,26,31,34,36,37]--><!-- NextX2 [4,5]-->
		<Ptbc contentHeight={contentHeight} contentWidth={contentWidth} on:nextPage={handleNextPage} on:previousPage={handlePreviousPage}/>
	{/if}

	{#if page_nextX2.includes(page)}
	<!-- NextX2 [4,5]-->

	{/if}

	{#if page_nextX3.includes(page)}
	<!-- NextX3 [9,10,11]-->
	{/if}

	{#if page_n.includes(page)}
	<!-- N [6,12]-->
		<PStart contentHeight={contentHeight} contentWidth={contentWidth} page={page} on:nextPage={handleNextPage}/>
	{/if}

	{#if page_s.includes(page)}
	<!-- S [15]-->

	{/if}

	{#if page_l.includes(page)}
	<!-- L [19,21,23,25,26,27,28,29,30,32,33,35]-->

	{/if}

	{#if page_nextP.includes(page)}
	<!-- NestP [38, 39]-->
	{/if}

	{#if page_ENG.includes(page)}
	<!-- ENG [40]-->
	{/if}

</body>

<style>

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
