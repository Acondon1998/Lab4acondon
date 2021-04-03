<script>
	import Todos from './Todos.svelte';
</script>

<main>
	<h1>To Do App</h1>
	<Todos />
	
</main>

<style>
	main {
		text-align: center;
		padding: 2rem;
		margin: 0 auto;
		font-family: 'Gill Sans', 'Gill Sans MT', Calibri, 'Trebuchet MS', sans-serif;
	}

	h1 {

		font-size: 2rem;
		
	}

	@media (min-width: 640px) {
		main {
			max-width: none;
		}
	}
</style>