<script lang="ts">
    import LogoComponent from "./SvelteLogo.svelte";
    import Logo from "../../assets/svelte.svg";

    let active: boolean = true;
    let theme: "light" | "dark" = "light";
    let color: string = "red";

</script>

<p class="blue">This text is blue</p>

<div class="logo">
    <!-- figure 1 -->
    <img alt="Svelte Logo" src={Logo}/>
    <!-- figure 2 -->
    <LogoComponent/>

</div>
<!-- figure 3 -->
<img alt="Svelte Logo" src={Logo}/>
<LogoComponent/>

<!-- Class attribute syntax -->
<li class={active ? "active" : ""}>TOP</li>
<li class:active={active}>TOP</li>
<li class:active>TOP</li>
<button class="button" class:dark={theme === "light"} class:active>Submit</button>

<!-- Style attribute syntax -->
<div style="color: red">Red color</div>
<div style:color="red">Red color</div>
<div style:color={color}>Use color variable</div>
<div style:color>Use color variable</div>
<div style="font-size: 1.5rem;" style:color style:background-color={theme === "light" ? "black" : "white"}> hello</div>

<style>
    /* style syntax */

    :global(body) {
        background-color: azure;
    }

    .blue {
        color: blue;
    }

    .logo :global(img) {
        /*
        Styles every <img> inside `.logo`, including child components.
        Applies to figure 1 and 2
        Does NOT apply to figure 3
        */
        width: 128px;
    }

    .logo img {
        /*
        Styles only <img> inside this component’s`.logo` scope (not child components).
        Does NOT apply to figure 2 and 3
        Applies to figure 1
        */
        border: 1px solid black;
    }

</style>