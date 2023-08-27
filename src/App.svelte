<script>
	// let firstName = "Shishir";
	// let lastName = "Sabbir";
	// let beltColor = "Orange";

	// let fullName = firstName + ' ' + lastName;
	// reactive value
	// $: fullName = `${firstName} ${lastName}`;

	// reactive statements
	// $: {
		// console.log(firstName);
		// console.log(beltColor);
	// }

	// people array
	let people = [
		{name: 'Yoshi', beltColor: 'Black', age: 25, id: 1},
		{name: 'Mario', beltColor: 'Blue', age: 23, id: 2},
		{name: 'Luigi', beltColor: 'Orange', age: 21, id: 3},
		{name: 'Link', beltColor: 'Red', age: 26, id: 4},
		{name: 'Chun-Li', beltColor: 'Green', age: 19, id: 5}
	];
	
	const handleInput = e => {
		beltColor = e.target.value;
	};

	const handleClick = (id) => {
		people = people.filter((person) => {
			return person.id != id;
		});
	};
</script>

<main>
	<h1>People Card</h1>
	<div class="container">
		{#each people as person (person.id)}
			<div class="box" style="border: 1px solid {person.beltColor};">
				<h3>{person.name}</h3>
				<p class="age">{person.age} years old</p>
				<p class="belt"><span style="color: {person.beltColor};">{person.beltColor}</span>-Belt Ninja</p>
				<button on:click={() => {handleClick(person.id)}}>Delete</button>
			</div>
		{:else}
			<p>No People to Show</p>
		{/each}
	</div>
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

	div.container {
		display: flex;
		align-items: center;
		justify-items: center;
		flex-wrap: wrap;
		flex-direction: column;

		/* width: 600px; */
	}

	p.belt {
		font-variant: small-caps;
		font-size: 1.2em;
		text-transform: capitalize;
	}

	p.age {
		/* font-variant: small-caps; */
		font-size: 1em;
		text-transform: capitalize;
	}

	div.box {
		width: 400px;
		height: 180px;
		/* border: 1px solid #9f9f9f; */
		margin: 10px;
		flex-shrink: 0;
	}

	@media (min-width: 640px) {
		main {
			max-width: none;
		}
	}
</style>