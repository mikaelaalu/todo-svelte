<script>
import { createEventDispatcher } from 'svelte';

const dispatch = createEventDispatcher();

let task = {
     title: '',
     completed : false
 }

const onSubmit = (e) => {
    e.preventDefault()
    dispatch('addtask', task)
    task = {
        title:'',
        completed:false
    }
}
</script>

<form on:submit={onSubmit} class='taskForm'>
    <label for='task'>Task</label>
    <input class='inputField' type='text'  bind:value={task.title}>
    <button class='submitBtn' type='submit'> Add task</button>
</form>