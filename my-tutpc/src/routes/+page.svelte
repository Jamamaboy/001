<script>
	let page = 1;
	let point = 0;
	let imgWidth = 0;
	let imgHeight = 0;
	let contentHeight = 0;

	import PStart from './nested-components/pStart.svelte';


	function handleImageLoad(event) {
		imgWidth = event.target.naturalWidth;
		imgHeight = event.target.naturalHeight;

		// คำนวณความสูงของเนื้อหาโดยใช้สัดส่วนของภาพ
		contentHeight = (imgHeight / imgWidth) * Math.min(window.innerWidth, imgWidth);
	}

	function handleNextPage() {
		page += 1;
		console.log(page);
	}

</script>

<body>
	<img src="./Img/{page}.png" alt="P{page}" on:load={handleImageLoad}>
	{#if page == 1}
	<!-- Start -->
		<PStart page={page} point={point} imgHeight={imgHeight} imgWidth={imgWidth} on:nextPage={handleNextPage}/>

	{:else if page == 2}
	<!-- TBC -->

	{:else if page == 3}
	<!-- NextX2 -->

	{:else if page == 3}
	<!-- NextX3 -->

	{:else if page == 3}
	<!-- N -->

	{:else if page == 15}
	<!-- S -->

	{:else if page == 3}
	<!-- L -->

	{:else if NestP.includes(page)}
	<!-- NestP -->

	{:else if page == 40}
	<!-- ENG -->

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
