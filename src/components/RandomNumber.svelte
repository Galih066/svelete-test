<script lang="ts">
    let randomNumber = $state(Math.floor(Math.random() * 10));
    let doubleIt = $state(0);

    $effect(() => {
        doubleIt = randomNumber * 2
    })
</script>

<h2>Random Number: {randomNumber}</h2>
<h2>Double Randomed Number: {doubleIt}</h2>
<button onclick={() => {
    randomNumber = Math.floor(Math.random() * 10);
    console.log(randomNumber);
}}>Click Me</button>