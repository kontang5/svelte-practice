<script lang="ts">
    let x: number = 1;

    $: square  = x * x;
    $: cube = x * x * x;

    let n = 1;
    let stars: string[];

    $: console.log(`Change n to ${n}.`);
    $: {
        const newStars = [];
        for (let i = 0; i < n; i++) {
            newStars.push(i %2 === 0 ? '*' : '');
        }
        stars = newStars;
    }

    let m = 1;

    $: if(m > 10) {
        alert("Overloading! Reset to 10");
        m = 10;
    }

</script>

<div>
    length of side:
    <button onclick={() => (x--)} disabled={x <= 1}>-</button>
    {x} m
    <button onclick={() => (x++)}>+</button>
</div>

<div>
    square: {square}m<sup>2</sup>
</div>
<div>
    cube: {cube}m<sup>3</sup>
</div>

<hr>
<div>
    {#each stars as star}{star}{/each}
</div>
<div>
    <button onclick={() => (n--)} disabled={n <= 1}>-</button>
    <button onclick={() => (n++)}>+</button>
</div>

<div>
    quantity: {m}
</div>
<div>
    <button onclick={() => (m--)} disabled={m <= 1}>-</button>
    <button onclick={() => (m++)}>+</button>
</div>
