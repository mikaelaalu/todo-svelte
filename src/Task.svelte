<script>
    import { createEventDispatcher } from 'svelte';

    const dispatch = createEventDispatcher();

	export  let title;
	export let completed;

    const completeTask = () => completed = true
    const deleteTask = (e) => {
        e.preventDefault()
        dispatch('deleteTask', title)
    }

</script>

<div class='task'>
    <h2 class='taskTitle'>{title}</h2>
    {#if completed}
    <p class='completed'>Completed</p>
    {:else}
    <button class='btn' on:click={completeTask}>Done</button>
    {/if}
    <button class='redBtn' on:click={deleteTask}>Delete task</button>
</div>