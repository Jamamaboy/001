<script>
	import "../app.css";
</script>


<body>

	<div class="block">
		<h1 class="logo">What is <br>your <span style="font-size: 2.4em; font-style: italic; font-weight: bold;">Toy?</span></h1>
		<h3 class="description">Learn what powers you possess</h3>
		<button type="button" class="text-white bg-gradient-to-r from-purple-700 to-pink-300 hover:bg-gradient-to-l focus:ring-4 focus:outline-none focus:ring-purple-200 dark:focus:ring-purple-800 font-medium rounded-lg text-sm px-5 py-2.5 text-center me-2 mb-2">Start</button>
	</div>

</body>

<style>
	body {
		width: 100%;
		height: 100vh;
		margin: 0;
		padding: 0;
		background-color: white;
		display: grid;
		place-items: center;
	}
	.block {
		display: grid;
		justify-items: center;
		align-items: center;
	}
	.logo {
		font-size: 2em;
		font-weight: bold;
	}
	.description {
		font-size: 1em;
		margin-bottom: 20px;
	}

</style>
