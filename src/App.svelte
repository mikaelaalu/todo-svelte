<script>
	import Navbar from './Navbar.svelte'
	import Task from './Task.svelte'
	import AddTask from './AddTask.svelte'

	let tasks = [
	{
		title: 'Buy groceries',
		completed: false
	},
	{
		title: 'Take a walk',
		completed: false
	}
	]
	const addTask = (e) => {
		const newTask = e.detail;
		tasks = [newTask, ...tasks]
	} 
	
	const deleteTask = (e) => {
		tasks = tasks.filter((task) => task.title != e.detail)
	}

</script>

<Navbar />
<div class='container'>
	<AddTask on:addtask={addTask}/>
	{#if tasks.length < 1}

		<p>Nothing to do :)</p>

	{:else}
	{#each tasks as task}

		<Task title={task.title} completed={task.completed} on:deleteTask={deleteTask} />

	{/each}
	{/if}
</div>
