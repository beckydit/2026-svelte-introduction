<!-- JAVASCRIPT (SCRIPT) -->
<script>
 let { 
    initialCount: count = $bindable(0), 
    willIncrement = () => {},
    didIncrement = () => {}
 } = $props();

 let doubled = $derived(count * 2);   

 const increment = () => {
    willIncrement(count)
    count++
    didIncrement(count)
 }
</script>

<h3>Counter</h3>

<!-- HTML (MARKUP)  -->
<button on:click={increment}>
    Clicks: {count}
</button>  

<span>doubled is {doubled}</span>