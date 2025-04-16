<script lang="ts">
    const name = "Svelte";
    const src = "https://picsum.photos/200/300";
    const alt = "Svelte logo";
    let firstName = $state('');
    let lastName = $state('');
    const fullName = $derived.by(() => {
        console.log('Fullname derived')
        return `${firstName} ${lastName}`;
    });
    let defaultName = $state('');
</script>

<!-- <img {src} {alt}/> -->
<input type="text" bind:value={firstName} />
<input type="text" bind:value={lastName} />
<input type="text" bind:value={defaultName} />
<h1>My fullname is {fullName || defaultName}!</h1>