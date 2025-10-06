<script lang="ts">
    let message = "";
    let value = "";

    function handleInput() {
        alert(`'${message}'is detected`);
        alert(`'${value}'is detected`);
        message = "";
    }

    const taxRate = 0.1;
    let price = 100;
    $: priceWithTax = Math.floor(price * (1 + taxRate));

    let isAccepted = false;

    // variable binding to radio buttons
    let size = 'M';

    // variable binding to checkboxes
    let options = [];

    let aspect = 1 / 1;

</script>

<input bind:value={message} type="text">
<input bind:value type="text">
<button on:click={handleInput}>Detect</button>

<hr>

<div>Price: $<input bind:value={price} type="number"></div>
<div>Price with tax: ${priceWithTax}</div>

<hr>

<label>
    <input bind:checked={isAccepted} type="checkbox">Agree
</label>
<div>
    <button disabled={!isAccepted}>Submit</button>
</div>

<hr>

<h4>Size</h4>
<label>
    <input bind:group={size} type="radio" value="S">
    Size: small
</label>
<label>
    <input bind:group={size} type="radio" value="M">
    size: medium
</label>
<label>
    <input bind:group={size} type="radio" value="L">
    size: large
</label>

<h4>Toppings</h4>
<label>
    <input bind:group={options} type="checkbox" value="Pepperoni">
    Pepperoni
</label>
<label>
    <input bind:group={options} type="checkbox" value="cheese">
    Extra cheese
</label>
<label>
    <input bind:group={options} type="checkbox" value="mushroom">
    Mushroom
</label>

<button>
    Size: {size}
    {#if options.length > 0}
        (Toppings: {options.join(', ')})
    {/if}
    Checkout
</button>

<hr>

<label>
    <input bind:group={aspect} type="radio" value={1 / 1}>
    1 : 1
</label>
<label>
    <input bind:group={aspect} type="radio" value={4 / 3}>
    4 : 3
</label>
<label>
    <input bind:group={aspect} type="radio" value={16 / 9}>
    16 : 9
</label>
<div style="width: 300px" style:height="{300 / aspect}px" style:background="gray">
</div>

<hr>

<select bind:value={size}>
    <option value="S">Small</option>
    <option value="M">Medium</option>
    <option value="L">Large</option>
</select>

<button>{size} Size order</button>

<hr>

<select multiple bind:value={options}>
    <option value="Pepperoni">Pepperoni</option>
    <option value="cheese">Extra cheese</option>
    <option value="mushroom">Mushroom</option>
</select>

<div>
    Toppings:
    {#if options.length > 0}
    {options.join(', ')}
    {:else}
    None
    {/if}
</div>