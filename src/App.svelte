<script lang="ts">
    // <script> block (optional)
    // Only available in this component
    // Apply TypeScript by adding the `lang="ts"` attribute

    import Box from "./lib/Box.svelte";
    import Button from "./lib/Button.svelte";
    import Card from "./lib/Card.svelte";
    import List from "./lib/List.svelte";
</script>

<!-- HTML tags with svelte syntax -->
<Box>
    <h3>Svelte</h3>
    <p>Svelte, the framework</p>
    <!-- Use components -->
    <Button label="Click me"/>
    <!-- Use {# } blocks -->
    {#if true}
        <div>
            <p>Svelte is awesome</p>
        </div>
    {/if}
</Box>

<Box/>

<Card>
    <div>
        related content
    </div>
    <!-- Insert title slot -->
    <h3 slot="title">Svelte</h3>
    <!-- Insert body slot -->
    <div slot="body">
        <p>Svelte, the framework</p>
    </div>

    <svelte:fragment slot="footer">
        <a href="https://svelte.dev">Learn more</a>
    </svelte:fragment>
</Card>

<List let:item={text}>
    <div class="item">{text}</div>
</List>

<List>
    <span slot="frameworks" let:item={text}>{text}</span>
</List>
<style>
    /* <style> block (optional) */
    /* Only available in this component */
    .item {
        color: blue;
    }
</style>