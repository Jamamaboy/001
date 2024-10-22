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

	{#if page == 6}
		<div class="as">
			<button on:click={() => handleClick(0, 1)}>ไม่มีอะไรหรอก คงเป็นแค่เสียงลม<br>ที่กระทบกับหน้าต่าง</button>
			<button on:click={() => handleClick(0, 1)}>ใจเริ่มสั่น ตัวคุณเองก็กลัว และเริ่ม<br>จินตนาการไปต่าง ๆ นา ๆ</button>
			<button on:click={() => handleClick(0, 2)}>คุณจะลุกขึ้นมาเปิดไฟ</button>
			<button on:click={() => handleClick(0, 2)}>เรามันแน่อยู่แล้ว ขอก้มลงไปดูใต้<br>เตียงเลยแล้วกัน !</button>
		</div>
	{/if}
	{#if page == 12}
		<div class="as">
			<button on:click={() => handleClick(0, 1)}>คุณมึนงงปนตกใจ พร้อมรีบก้าวลงจากรถ<br>เข้าไปอุ้มแมวตัวนั้น</button>
			<button on:click={() => handleClick(0, 1)}>คุณตื่นเต้น พร้อมลุกจากรถไปอุ้มเจ้า<br>เหมียวเดินทางไปด้วยกัน</button>
			<button on:click={() => handleClick(0, 2)}>คุณฉะชะโงกหน้าออกไปดูลาดเลา เจ้าแมว<br>เพื่อที่จะได้พิจารณามัน</button>
			<button on:click={() => handleClick(0, 2)}>คุณคิดว่ามันแปลกเกินไปที่แมวจะอยู่ที่นี่<br>และคงไม่ดีนักที่จะไปยุ่งกับมัน</button>
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
		grid-template-rows: 45% 45% 10%;
		width: 100%;
	}
	.as {
		height: 100%;
		width: 60%;
		display: grid;
		align-items: center;
		grid-template-rows: 1fr 1fr 1fr 1fr;
		gap: 10%;
		/* background-color: aqua;	 */
	}
	.as button {
		font-family: 'CloudLoop';
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
