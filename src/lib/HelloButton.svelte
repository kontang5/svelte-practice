<script lang="ts">
    import { createEventDispatcher} from "svelte";

    const dispatch = createEventDispatcher<{ hello: string }>();
    function handleClick() {
        dispatch("hello", "こんにちは")
    }
</script>

<button on:click={handleClick}>Click Here</button>
