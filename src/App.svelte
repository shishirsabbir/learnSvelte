<script>
	let input_field = "Orange";
	
	const handleInput = e => {
		input_field = e.target.value;
	}
</script>

<main>
	<h1>Type Anything</h1>
	<p style="color: {input_field};">{input_field}</p>
	<input type="text" bind:value={input_field}>
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
		font-size: 1.2em;
	}

	@media (min-width: 640px) {
		main {
			max-width: none;
		}
	}
</style>