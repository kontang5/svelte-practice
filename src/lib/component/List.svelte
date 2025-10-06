<script lang="ts">
    let array: string[] = ["Svelte", "React", "Vue", "Angular"]
</script>

{#each array as e}
    <slot item={e}/>
    <slot name="frameworks" item={e}/>
{/each}