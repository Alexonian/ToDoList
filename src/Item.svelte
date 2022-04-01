<script>
    export let text;
    export let checked;
    export let removeItem;
    export let toggleDone;
</script>

<div class="listCont">
    <input class="box" bind:checked={checked} on:change={toggleDone} type="checkbox"> 
    <span class:checked={checked}>{text}</span>
    <button type="button" on:click={removeItem}></button>
</div>

<style>

    .checked {
        text-decoration: line-through;
    }
    
    .box {
        margin: 2px;
        width: 1.5rem;
        height: 1.5rem;
    }

    button {
        background-image: url("/xMark.png");
        background-position: center;
        background-size: contain;
        background-repeat: no-repeat;
        background-color: white;
        border: none;
        margin: 2px;
        width: 1.5rem;
        height: 1.5rem;
    }

    .listCont {
        display: flex;
        width: 20rem;
        height: 2rem;
        justify-content: space-between;
        background-color: white;
        align-items: center;
        padding: 1rem;
        margin: 1rem 0 0 0;
        border-radius: 0.5rem;
        text-align: center;
        
        font-family: 'Gill Sans', 'Gill Sans MT', Calibri, 'Trebuchet MS', sans-serif;
        font-size: 1.5rem;
    }
</style>