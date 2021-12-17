<script>
	export  let title;
	export let completed;
    const completeTask = ()=> completed = true
</script>

<div class='task'>
    <h2 class='taskTitle'>{title}</h2>
    {#if completed}
    <p class='completed'>Completed</p>
    {:else}
    <button class='btn' on:click={completeTask}>Done</button>
    {/if}
</div>