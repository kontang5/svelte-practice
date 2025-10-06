<script>
    let time;
</script>

<video
        bind:currentTime={time}
        controls
        src="https://interactive-examples.mdn.mozilla.net/media/cc0-videos/flower.mp4"
        width="320"
>
    <track kind="captions">
</video>

<div>
    {#each [1, 2, 3, 4, 5] as t}
        <button on:click={() => (time = t)}>move to {t}</button>
        {/each}
</div>

{#if time !== undefined}
    <div>playing around {time}</div>
{/if}