<script>
    export let selected;
    export let options;
    let isOpen = false;

    const handleButtonClick = () => {
        isOpen = !isOpen;
    };
    const handleOptionClick = (option) => () => {
        selected = option;
        isOpen = false;
    };

</script>

<button on:click={handleButtonClick}>{selected}</button>
{#if isOpen}
    <ul>
        {#each options as option}
            <li on:click={handleOptionClick(option)}>{option}</li>
        {/each}
    </ul>
{/if}