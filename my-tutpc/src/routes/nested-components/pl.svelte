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

</script>

<div class="content" style="height: {contentHeight}px; width: {contentWidth}px;">

	<div class="space"></div>

	{#if page == 19}
		<div class="as">
			<button on:click={() => handleClick(1, 1)}>คิดติดตลกว่าจะคุยกับผียังไงดี?</button>
			<button on:click={() => handleClick(2, 1)}>นั่งคิดสักพัก และ ตัดสินใจ<br>ไปที่อื่นก่อน</button>
			<button on:click={() => handleClick(3, 1)}>ผีมีจริงที่ไหน</button>
			<button on:click={() => handleClick(4, 1)}>อยากจะเล่นกับพวกผีจัง<br>เลย! แกล้งกลับดีไหม?</button>
		</div>
	{/if}

	{#if page == 21}
		<div class="as">
			<button on:click={() => handleClick(1, 1)}>เอาไปขายซะ</button>
			<button on:click={() => handleClick(2, 1)}>ต้องแลกกับอะไรหรือเปล่านะ?</button>
			<button on:click={() => handleClick(3, 1)}>จะปรุงยาวิเศษที่ขึ้นชื่อว่าปรุงยากที่สุด</button>
			<button on:click={() => handleClick(4, 1)}>ยานี่มีไว้ทำอะไร ไม่อยากรับเลย...</button>
		</div>
	{/if}

	{#if page == 23}
		<div class="as">
			<button on:click={() => handleClick(1, 1)}>ลองเล่นเพราะอยากรู้ว่าจะสนุกไหม ?</button>
			<button on:click={() => handleClick(2, 1)}>อยากเล่น แต่รถนี้ปลอดภัยไหมเนี่ย ?</button>
			<button on:click={() => handleClick(3, 1)}>ไม่เล่นเพราะกลัวว่าอาจบาดเจ็บ</button>
			<button on:click={() => handleClick(4, 1)}>ไม่เล่นเพราะไม่ชอบการแข่งขัน</button>
		</div>
	{/if}

	{#if page == 25}
		<div class="as">
			<button on:click={() => handleClick(1, 1)}>พยายามคิดหาวิธีออก</button>
			<button on:click={() => handleClick(2, 1)}>ฉันเข้ามาทำอะไรในนี้เนี่ย?</button>
			<button on:click={() => handleClick(3, 1)}>น่าตื่นเต้น อยากลอง!</button>
			<button on:click={() => handleClick(4, 1)}>ไปเล่นเครื่องอื่นดีกว่าไหมเนี่ย?</button>
		</div>
	{/if}

	{#if page == 27}
		<div class="as">
			<button on:click={() => handleClick(1, 1)}>รอคนอื่นอยู่ข้างนอกดีกว่า</button>
			<button on:click={() => handleClick(2, 1)}>ถ้าเข้าไปต้องเกิดเรื่องไม่ดีแน่ ๆ</button>
			<button on:click={() => handleClick(3, 1)}>ลองเล่นสักครั้งแล้วกัน</button>
			<button on:click={() => handleClick(4, 1)}>เป็นการผจญภัยที่ท้าทายมาก!</button>
		</div>
	{/if}

	{#if page == 28}
		<div class="as">
			<button on:click={() => handleClick(1, 1)}>ขับพุ่งเข้าไปเล่นทันที</button>
			<button on:click={() => handleClick(2, 1)}>จอดรถก่อน ดูคนอื่นเล่นก่อนดีกว่า</button>
			<button on:click={() => handleClick(3, 1)}>เรียกน้องแมวมาเล่นด้วยกัน</button>
			<button on:click={() => handleClick(4, 1)}>หาวิธีลงจากรถดีกว่า</button>
		</div>
	{/if}

	{#if page == 29}
		<div class="as">
			<button on:click={() => handleClick(1, 1)}>การ์ตูนแอ๊กชันที่สนุกสุดเหวี่ยง</button>
			<button on:click={() => handleClick(2, 1)}>หนังที่เข้าถึงจิตใจคน</button>
			<button on:click={() => handleClick(3, 1)}>สารคดี</button>
			<button on:click={() => handleClick(4, 1)}>หนังเสียดสีสังคม</button>
		</div>
	{/if}

	{#if page == 30}
		<div class="as">
			<button on:click={() => handleClick(1, 1)}>ครอบครัว</button>
			<button on:click={() => handleClick(2, 1)}>คู่แข่ง</button>
			<button on:click={() => handleClick(3, 1)}>พี่น้อง</button>
			<button on:click={() => handleClick(4, 1)}>เพื่อน</button>
		</div>
	{/if}

	{#if page == 32}
		<div class="as">
			<button on:click={() => handleClick(1, 1)}>ไป ๆๆ นั่งด้วยกันเถอะ!</button>
			<button on:click={() => handleClick(2, 1)}>น่าตื่นเต้นมาก! เราเปิดเพลงเองได้ไหม?</button>
			<button on:click={() => handleClick(3, 1)}>ก็น่าเล่นนะ ถ้ามีเพลงที่ใช่</button>
			<button on:click={() => handleClick(4, 1)}>แค่เครื่องเล่นหมุน ๆ ไม่เห็นน่าสนใจเลย</button>
		</div>
	{/if}

	{#if page == 33}
		<div class="as">
			<button on:click={() => handleClick(1, 1)}>ทัศนียภาพที่ไกลสุดลูกหูลูกตา</button>
			<button on:click={() => handleClick(2, 1)}>เครื่องเล่นนี้ได้มาตรฐานไหม?</button>
			<button on:click={() => handleClick(3, 1)}>ชิงช้านี้มีอะไรเด่นที่ดึงดูดคนมาเล่น?</button>
			<button on:click={() => handleClick(4, 1)}>ชิงช้าจะหมุนกลิ้งได้ไหม</button>
		</div>
	{/if}

	{#if page == 35}
		<div class="as">
			<button on:click={() => handleClick(0, 1)}>ขึ้นไปนั่งด้วยความรู้สึกอยากพักเหนื่อยเต็มทน</button>
			<button on:click={() => handleClick(0, 1)}>สอบถามเส้นทางกับคนขับก่อนจะขึ้นไปนั่ง</button>
			<button on:click={() => handleClick(0, 2)}>คุณตัดสินใจไม่ขึ้นเพราะบนรถ<br>ไม่มีผู้โดยสารคนอื่น</button>
			<button on:click={() => handleClick(0, 2)}>ถึงแม้งว่าจะเหนื่อย<br>แต่คุณก็ยืนหยัดที่จะเดินต่อไป</button>
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
		font-display: swap;
	}
	.content {
		display: grid;
		z-index: 1;
		justify-items: center;
		align-items: center;
		grid-template-rows: 43% 42% 15%;
		width: 100%;
	}
	.as {
		height: 100%;
		width: 60%;
		display: grid;
		align-items: center;
		grid-template-rows: 1fr 1fr 1fr 1fr;
		gap: 5%;
		/* background-color: aqua;	 */
	}
	.as button {
		font-family: 'CloudLoop', sans-serif;
		font-size: 18px;
		color: darkslategrey;
		height: 100%;
		width: 100%;
		border-radius: 20px;
		border: 1px;
		background-color: #ffffff;
		opacity: 0.85;
	}
	.space {
		height: 100%;
	}

</style>
