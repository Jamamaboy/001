<script>
	let page = 1;
	let point = 0;
	let imgWidth = 0;
	let imgHeight = 0;

	import P01 from './nested-components/p01.svelte';

	function handleImageLoad(event) {
		imgWidth = event.target.naturalWidth;
		imgHeight = event.target.naturalHeight;
	}

	function handleNextPage() {
		page += 1;
	}
</script>

<body>
	<img src="./Img/{page}.png" alt="P{page}" on:load={handleImageLoad}>
	<P01 page={page} point={point} imgHeight={imgHeight} imgWidth={imgWidth} on:nextPage={handleNextPage}/>
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
