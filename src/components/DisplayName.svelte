<script lang="ts">
    const name = "Svelte";
    const src = "https://picsum.photos/200/300";
    const alt = "Svelte logo";
    let firstName = $state('Galeh');
    let lastName = $state('Imanda');
    const fullName = $derived.by(() => {
        return `${firstName} ${lastName}`;
    });
    let defaultName = $state('Galeh Imanda');
</script>

<!-- <img {src} {alt}/> -->
<input type="text" bind:value={firstName} />
<input type="text" bind:value={lastName} />
<input type="text" bind:value={defaultName} />
<h1>My fullname is {fullName || defaultName}!</h1>