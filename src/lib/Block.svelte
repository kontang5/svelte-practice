<script lang="ts">
    let name: string = "";
    let isLoggedIn: boolean = false;

    function toggle() {
        isLoggedIn = !isLoggedIn;
    }

    let rate: number = 0;

    let products: object[] = [
        {name: "Product A", price: 100},
        {name: "Product B", price: 200},
        {name: "Product C", price: 300},
    ];

    let promise = new Promise((resolve, reject) => {
        setTimeout(() => resolve("3seconds passed"), 3000);
    });
</script>

<!-- Common syntax -->

<div>Hello
    {#if name}{name}{:else}Guest{/if}
</div>
<!-- Following code is not valid -->
<!--<button {#if !valid}disabled{/if}>Click me</button>>-->

<!-- {#if} Block -->

{#if isLoggedIn}
    <button on:click={toggle}>Logout</button>
{:else}
    <button on:click={toggle}>Login</button>
{/if}

{#if rate >= 8}
    <p>High rate</p>
{:else if rate >= 4}
    <p>Medium rate</p>
{:else}
    <p>Low rate</p>
{/if}

<!-- {#each} Block -->

<ul>
    {#each products as p, i}
        <li>No.{i}: {p.name} - ${p.price}</li>
    {:else}
        <li>There is no product</li>
    {/each}
</ul>

<!-- {#await} Block -->

{#await promise}
    <p>Promise waiting for resolve...</p>
{:then message}
    <p>{message}</p>
{:catch error}
    <p>{error}</p>
{/await}

{#await promise then message}
    <p>{message}</p>
{/await}

{#await promise catch error}
    <p>{error}</p>
{/await}