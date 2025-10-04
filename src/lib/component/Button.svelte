<script lang="ts">
    export let label: string = "Default";
    // Default attribute value
    export let disabled: boolean = false;
</script>

<button {disabled}>
    {label}
</button>
