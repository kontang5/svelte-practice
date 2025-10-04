<script lang="ts">
    let name: string = "Svelte";
    let value: number = 123;
    let imageURL: string = "https://github.com/sveltejs/branding/raw/master/svelte-logo.png";
    let imageAlt: string = "Svelte Logo";
    let next: number = 1;
    let href: string = "https://svelte.dev"
    let disabled: boolean = true;
    let attributes: object = {
        type: 'submit',
        disabled: false,
        class: 'button'
    };
</script>

<!-- HTML tags -->

<p class="text">Hello, Svelte!</p>
<img src="https://github.com/sveltejs/branding/raw/master/svelte-logo.png" alt="Svelte Logo">

<!-- Dynamic content -->

<p>The current time is {new Date().toLocaleTimeString()}</p>
<h1>Hello, {name}!</h1>
<div>{(/^[A-Za-z]+$/).test(value.toString()) ? "OK" : "NG"}</div>

<!-- Dynamic attributes -->

<img src={imageURL} alt={imageAlt}>
<a href="page/{next}">Next page</a>
<!--<a href={href}>Svelte Official Webpage</a>-->
<a {href}>Svelte Official Webpage</a>
<button {disabled}>Out of stock</button>
<!--<button type={attributes.type} disabled={disabled} class={attributes.class}>Button</button>-->
<button {...attributes}>Button</button>