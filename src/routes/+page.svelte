<!-- JAVASCRIPT (SCRIPT) -->
<script>
 import {website} from '$lib/state.svelte.js';

 import Canvas from '$lib/components/Canvas.svelte';
 import Counter from '$lib/components/Counter.svelte';
 import TodoList from '$lib/components/TodoList.svelte';
 import TItleEditor from '$lib/components/TItleEditor.svelte';
 
 let count = $state(5); 

 $inspect("count is:", count);
</script>   

<!-- HTML (MARKUP) -->
<h1>{website.title}</h1>
<p>Visit <a href="https://svelte.dev/docs/kit">svelte.dev/docs/kit</a> to read the documentation</p>

<TItleEditor />

<Counter 
   bind:initialCount={count} 
   willIncrement={(count) => console.log("count was:",count)}
   didIncrement={(count) => console.log("count has become:",count)}
   />

{#if count > 10 && count < 20}
    <p>count from parent is {count}</p>
{:else if count > 30}
    <p>wow that's a lot of clicks</p>
{:else}
    <p>count is not in range</p>
{/if}

<Canvas />

<TodoList />


<!-- CSS (STYLE) -->
<style>
    h1 {color: palevioletred;}
    p {color: rebeccapurple;}
</style>