<div class="card">
    {#if $$slots.title}
        <div class="title">
            <slot name="title"/>
        </div>
    {/if}
    <div class="body">
        <slot name="body"/>
    </div>
    <slot/>
    <slot name="footer"/>
</div>

<style>
    .card {
        border: 1px solid lightgray;
    }

    .title {
        border-bottom: 1px solid lightgray;
        padding: .5em 1em;
    }

    .body {
        padding: .5em 1em;
    }
</style>