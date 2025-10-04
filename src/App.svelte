<script lang="ts">
    // <script> block (optional)
    // Only available in this component
    // Apply TypeScript by adding the `lang="ts"` attribute
    import HelloButton from "./lib/component/HelloButton.svelte";
    import CustomButton from "./lib/component/CustomButton.svelte";

    function handleClick() {
        alert("Clicked!");
    }
    function handleSubmit(event: Event) {
        // event.preventDefault();
        const formData = new FormData(event.target as HTMLFormElement);
        alert(`form submitted: ${formData.get('key')}`);
    }
    function handleHello(event: CustomEvent<string>) {
        alert(event.detail);
    }
</script>

<!-- HTML tags with svelte syntax -->
<button on:click={handleClick}>Click me</button>
<button on:click={() => alert("Clicked!")}>Click</button>

<form on:submit={handleSubmit}>
    <input type="search" name="keyword" placeholder="Search..." />
    <button type="submit">Search</button>
</form>

<a href="https://svelte.dev/tutorial" on:click|preventDefault={handleClick}>Svelte Tutorial</a>

<div on:click|capture|stopPropagation={() => alert("div clicked")}>
    <button on:click|preventDefault={handleClick}>click</button>
</div>

<HelloButton on:hello={handleHello}/>

<CustomButton on:click={handleClick}>Custom Button</CustomButton>
<style>
    /* <style> block (optional) */
    /* Only available in this component */

</style>