<script>
    import CustomSelect from "./lib/reactivity/CustomSelect.svelte";

    let fruit = "apple";
</script>

<div>Choosing: {fruit}</div>

<CustomSelect bind:selected={fruit} options={["apple", "banana", "orange"]} />
