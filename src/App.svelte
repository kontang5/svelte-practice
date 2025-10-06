<script>
    import CustomForm from "./lib/reactivity/CustomForm.svelte";

    let customForm;

    function handleClick() {
        customForm.reset();
    }
</script>

<CustomForm bind:this={customForm} />

<button on:click={handleClick}>Reset</button>