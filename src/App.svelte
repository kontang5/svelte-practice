<script lang="ts">
    let count: number = 0;

    function handleClick() {
        // count = count + 1;
        // count += 1;
        count++;
    }
</script>

<button on:click={handleClick}>{count} times clicked!</button>
