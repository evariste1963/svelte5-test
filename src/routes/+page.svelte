<script lang="ts">
	import TaskForm from '../components/task-form.svelte';

	type Task = {
		id: string;
		title: string;
		done: boolean;
	};

	let message = 'Tasks App';
	let tasks = $state<Task[]>([]);

	function addTask(newTask: string) {
		tasks.push({
			id: crypto.randomUUID(),
			title: newTask,
			done: false
		});
	}
</script>

<main>
	<h1>{message}</h1>
	<TaskForm {addTask} />
	<section>
		{#each tasks as task}
			<article>
				{task.title}
			</article>
		{/each}
	</section>
</main>

<style>
	main {
		margin: 1rem auto;
		max-width: 800px;
	}
</style>
