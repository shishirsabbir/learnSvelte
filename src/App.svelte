<script>
	let beltColor = "orange" ;
	const handle_belt = () => {
		beltColor = "black"
	}
</script>

<main>
	<h1>Hello, Shishir</h1>
	<p><span>{beltColor}</span> Belt Ninja</p>
	<button on:click={handle_belt}>Belt Update</button>
</main>

<style>
	main {
		text-align: center;
		padding: 1em;
		max-width: 240px;
		margin: 0 auto;
	}

	h1 {
		color: #ff3e00;
		text-transform: uppercase;
		font-size: 4em;
		font-weight: 100;
	}

	p {
		font-variant: small-caps;
	}

	p > span {
		font-size: 1.2em;
		font-weight: bold;
	}

	@media (min-width: 640px) {
		main {
			max-width: none;
		}
	}
</style>