<script lang="ts">
	let newTask = $state(''); //rune
	let {
		addTask
	}: {
		addTask: (newTask: string) => void;
	} = $props();

	function formSubmitted(e: SubmitEvent) {
		e.preventDefault();
		addTask(newTask);
		newTask = '';
	}
</script>

<form onsubmit={formSubmitted}>
	<label>
		Task
		<input name="newTask" bind:value={newTask} />
	</label>
	<div class="button-container">
		<button>submit</button>
	</div>
</form>

<style>
	form {
		margin-bottom: 1rem;
	}
	.button-container {
		display: flex;
		justify-content: end;
	}
</style>
