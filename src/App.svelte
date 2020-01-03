<script>
let title = 'Recipe title';
let ingredients = [
	{
		amount: '1T',
		name: 'Vanilla'
	},
];
let steps = [
	'Add vanilla'
];

const addIngredient = () => {
	ingredients = [
		...ingredients,
		{
			amount: '1T',
			name: 'Vanilla'
		}
	];
};
const addStep = () => {
	steps = [
		...steps,
		''
	];
};
</script>

<main>
	<div>
		<input type="text" bind:value={title} />

		<h3>Ingredients</h3>
		<div class="ingredients">
		{#each ingredients as ingredient}
			<input type="text" bind:value={ingredient.amount} />
			<input type="text" bind:value={ingredient.name} />
		{/each}
		</div>
		<button on:click={addIngredient}>Add Ingredient</button>

		<h3>Steps</h3>
		<div>
		{#each steps as step}
			<input type="text" bind:value={step} />
		{/each}
		</div>
		<button on:click={addStep}>Add Step</button>
	</div>
	<div class="recipe">
		<h1>{title}</h1>
		<h3>Ingredients</h3>
		<div class="ingredients">
		{#each ingredients as ingredient}
			<div>{ingredient.amount}</div>
			<div>{ingredient.name}</div>
		{/each}
		</div>
		<h3>Steps</h3>
		<ol>
		{#each steps as step}
			<li>{step}</li>
		{/each}
		</ol>
	</div>
</main>

<style>
main {
	font-family: Arial, Helvetica, sans-serif;
	display: grid;
	grid-template-columns: 1fr 1fr;
	grid-column-gap: 1em;
}

input {
	width: 100%;
	font-size: large;
}

.recipe {
	border: 1px solid #666;
	padding: 1em;
}

.recipe h1 {
	border-bottom: 1px solid #ccc;
}

.ingredients {
	display: grid;
	grid-template-columns: 10% 90%;
	grid-gap: 0.5em;
}
</style>