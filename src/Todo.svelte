<script>
    import Item from './Item.svelte'
    let newItem;
    let todoList = [];
    function addToList() {
        if (!newItem) return;
        todoList = [...todoList, {
            text: newItem,
            checked: false,
        }];
        newItem = '';
    }
    function removeFromList(n) {
        todoList.splice(n, 1);
        todoList = todoList;
    }
    function toggleDone(index, v) {
        v =!v;
        todoList[index].checked = v;
        todoList = todoList;
    }

</script>

<form on:submit|preventDefault={addToList}>
    <input bind:value={newItem}>
</form>
<ul>
    {#each todoList as item, index}
        <Item 
            text={item.text} 
            checked={item.checked}
            toggleDone={() => toggleDone(index, item.checked)}
            removeItem={() => removeFromList(index)}
        />
    {/each}
</ul>


<style>
    ul {
        list-style: none;
        display: flex;
        padding: 0;
        margin: 1rem 0 0 0;
        flex-direction: column;
        align-items: center;
    }
    input {
        border-radius: 0.5rem;
        background-color: rgb(255, 191, 112);
        border: none;
        font-family: 'Gill Sans', 'Gill Sans MT', Calibri, 'Trebuchet MS', sans-serif;
        font-size: 1.5rem;
    }
</style>