<script>
    import { onMount } from "svelte";
    let users = [];
    onMount(async () => {
        const res = await fetch("https://jsonplaceholder.typicode.com/pos");
        const json = await res.json();
        users = json;
    });
</script>

{#each users as user}
    <h3>{user.title}</h3>
    <br />
    <p>{user.body}</p>
{/each}

<style>
    h3 {
        color: red;
    }
</style>
