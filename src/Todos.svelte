<script>
    import {fly} from 'svelte/transition'
    let task='';
    let toDo=[];

    function addItem() {
        if (!task) return;
        toDo = [...toDo, {
            text: task,
            status: false

        }];
        task='';
        console.log(toDo)
    }

    function removeItem(index) {
        toDo.splice(index, 1);
        toDo = toDo;
    }

    
</script>


<form on:submit|preventDefault={addItem}>
    <input class= "input is-rounded input is-small" bind:value={task}>
</form>

<ol class="todo-list">
    {toDo.filter(item=>item.status==true).length}
    Tasks of 
    {toDo.length}
    have been completed
    {#each toDo as item, index}
        <li transition:fly= "{{ y: 21, duration: 250 }}">
            <input bind:checked={item.status} class="checkbox" type="checkbox">
            <span>{item.text}</span>
            <i class="fa fa-trash-o" on:click={() => removeItem(index)}></i>
           
        </li>
    {/each}
</ol>


<style>
    .todo-list {
        display:contents;
        list-style: none;
        padding: 10px;
    }

</style>