<script lang="ts">
    // <script> block (optional)
    // Only available in this component
    // Apply TypeScript by adding the `lang="ts"` attribute
    import Button from "./lib/Button.svelte";
    import UserProfile from "./lib/UserProfile.svelte";
    import PropsTest from "./lib/PropsTest.svelte";

    let buttonLabel: string = "Subscribe";
    let label: string = "Label";

    let john = {
        name: "John",
        id: "john01",
        bio: "svelter"
    }

    let props = {
        label: "Submit",
        disabled: true,
    }

    export let containerClass: string = "button-container";
</script>

<!-- HTML tags with svelte syntax -->

<!-- Transfer attributes to the component -->
<Button label={buttonLabel}/>
<Button {label}/>
<Button label="Direct string"/>

<UserProfile user={john}/>

<Button label={label} disabled={true}/>
<Button {...props}/>

<PropsTest foo="Test" bar={42}/>

<div class={containerClass}>
    <Button {...$$props}/>
    <Button {...$$restProps}/>
</div>

<style>
    /* <style> block (optional) */
    /* Only available in this component */
</style>