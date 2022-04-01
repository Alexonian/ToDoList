<script>
	import Todo from './Todo.svelte';
</script>

<main>
	<heading class="heading">
		<h1>To-Do List</h1>
		<Todo />
	</heading>
</main>

<style>
	main {
		padding: 1em;
		max-width: 240px;
		margin: 0 auto;
	}

	h1 {
		color: #ff9a79;
		text-transform: uppercase;
		font-size: 5em;
		font-weight: 500;
	}


	.heading {
		text-align: center;
	}

	@media (min-width: 640px) {
		main {
			max-width: none;
		}
	}
</style>