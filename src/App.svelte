<script lang="ts">
    let todos: string[] = [];

    function handleClick() {
        // todos.push("new Task");
        // todos = todos;
        todos = [...todos, "new Task"];
    }

    let range = {min: 0, max: 10};
    let values: number[] = [];

    $: {
        const newValues = [];
        for (let i = range.min; i <= range.max; i++) {
            newValues.push(i);
        }
        values = newValues;
    }

    function handleMinChange(event) {
        range.min = parseInt(event.target.value);
    }

    function handleMaxChange(event) {
        range.max = parseInt(event.target.value);
    }

    // Can't detect state changes
    let setting1 = {volume: {value: 50},
    };

    function updateVolume(diff: number) {
        const volume = setting1.volume;
        // The left side doesn't have a variable `setting`.
        volume.value += diff;
    }

    function handleReset() {
        // passing variables as argument
        resetVolume({args: setting1});
    }

    function resetVolume({args}: { args: any }) {
        args.volume = {value: 50};
    }

    let setting2 = {
        volume: {value: 50},
    }

    function updateVolume2(diff: number) {
        // Directly referencing variable `setting2`
        setting2.volume.value += diff;
    }
    function handleReset2() {
        resetVolume2();
    }
    function resetVolume2() {
        // Directly update variable `setting2`
        setting2.volume = {value: 50};
    }
</script>

<ul>
    {#each todos as todo}
        <li>{todo}</li>
    {/each}
</ul>
<button on:click={handleClick}>Add Task</button>

<div>
    <input max={range.max} min={0} on:change={handleMinChange} type="number" value={range.min}>
    <input max={100} min={range.min} on:change={handleMaxChange} type="number" value={range.max}>
</div>
{#each values as value}
    <button>{value}</button>
{/each}

<div>
    Volume: {setting1.volume.value}%
</div>

<button on:click={() => updateVolume(-10)}>Decrease</button>
<button on:click={() => updateVolume(10)}>Increase</button>
<button on:click={handleReset}>Reset</button>

<hr>

<div>
    Volume: {setting2.volume.value}%
</div>

<button on:click={() => updateVolume2(-10)}>Decrease</button>
<button on:click={() => updateVolume2(10)}>Increase</button>
<button on:click={handleReset2}>Reset</button>
