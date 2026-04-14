<script>
    let todos = $state([
        { title: "Assignment 1", done: false },
        { title: "<i>Assignment 2</i>", done: true },
        { title: "Assignment 3", done: false }
    ]);

    let groceries = $state([
        { title: "Apple", done: false },
        { title: "<b>Bread</b>", done: false },
        { title: "Salmon", done: false }
    ]);

</script>

{#snippet todoItem(todo)}
    <li>
        <label>
            <input type="checkbox" bind:checked={todo.done}>
            {@html todo.title}
        </label>
    </li>
{/snippet}

<h3>Todo List</h3>

<ul>
    {#each todos as todo}
        {@render todoItem(todo)}
    {/each}
</ul>

<h3>Grocery List</h3>

<ul>
    {#each groceries as grocery}
            {@render todoItem(grocery)}
    {/each}
</ul>

<style>
    label :global {
        i {color: rgb(11, 75, 149);}
        b {color: rgb(0, 141, 151);}
    }
</style>

