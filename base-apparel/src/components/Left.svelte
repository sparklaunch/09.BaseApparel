<script lang="ts">
    import Logo from "./Logo.svelte";
    import Content from "./Content.svelte";
    import Form from "./Form.svelte";
</script>

<div id="left">
    <Logo />
    <Content />
    <Form />
</div>

<style>
    #left {
        width: 55%;
        background-image: url("/assets/bg-pattern-desktop.svg");
        background-size: cover;
        background-repeat: no-repeat;
        padding: 50px 100px;
    }
</style>
