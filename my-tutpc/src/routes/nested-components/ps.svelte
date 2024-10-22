<script>
	import { createEventDispatcher } from "svelte";
	export let contentHeight;
	export let contentWidth;
	export let page;

	const dispatch = createEventDispatcher();

	/**
     * @param {number | undefined} [additionalPoint]
     * @param {number} [pageIncrement]
     */
	 function handleClick(additionalPoint, pageIncrement) {
		dispatch('nextPage', { additionalPoint, pageIncrement });
	}
	console.log(page);


</script>

<div class="content" style="height: {contentHeight}px; width: {contentWidth}px;">
	<div class="space"></div>
	{#if page == 15}
		<div class="as">
			<button on:click={() => handleClick(0, 1)}>แมวดูมีความแฟนตาซีแตกต่างจากแมวปกติทั่วไป</button>
			<button on:click={() => handleClick(0, 1)}>แมวดูมีกิริยาท่าทางที่สุภาพเรียบร้อย</button>
			<button on:click={() => handleClick(0, 1)}>รูปร่างเหมือนแมวธรรมดาทั่วไปตัวหนึ่ง</button>
			<button on:click={() => handleClick(0, 1)}>แมวดูมุ่งมั่น ตื่นเต้นที่จะได้ผจญภัยครั้งนี้ไปด้วยกัน</button>
		</div>
	{/if}
	<div class="space"></div>
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
		grid-template-rows: 55% 45% 10%;
		width: 100%;
	}
	.as {
		height: 100%;
		width: 60%;
		display: grid;
		align-items: center;
		grid-template-rows: 1fr 1fr 1fr 1fr;
		gap: 5%;
		/* background-color: aqua; */
	}
	.as button {
		font-family: 'CloudLoop', sans-serif;
		font-size: 16px;
		color: darkslategrey;
		height: 100%;
		width: 100%;
		border-radius: 20px;
		border: 1px;
		background-color: #ffffff;
	}
	.space {
		height: 100%;
	}

</style>
