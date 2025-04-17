<script lang="ts">
    const name = "Svelte";
    const src = "https://picsum.photos/200/300";
    const alt = "Svelte logo";
    let firstName = $state('Test');
    let lastName = $state('Ing');
    const fullName = $derived.by(() => {
        console.log('Fullname derived')
        return `${firstName} ${lastName}`;
    });
    let defaultName = $state('');

    $effect(() => {
        if (defaultName || fullName) {
            console.log('User has default name of fullname')
        }
    })
</script>

<!-- <img {src} {alt}/> -->
<input
    type="text"
    value={firstName}
    oninput={event => {
        firstName = event.currentTarget.value;
        console.log(fullName)
    }}
/>
<input type="text" bind:value={lastName} />
<input type="text" bind:value={defaultName} />
<h1>My fullname is {fullName || defaultName}!</h1>