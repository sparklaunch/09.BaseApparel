<script lang="ts">
    import Logo from "./Logo.svelte";
    import Content from "./Content.svelte";
    import Form from "./Form.svelte";
    export let offset;
</script>

<div id="left" style="padding-bottom: {offset + 80}px;">
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
        padding: 50px 150px;
    }
    @media all and (max-width: 1440px) {
        #left {
            width: 100%;
            padding: 80px 30px;
            text-align: center;
            height: auto;
        }
    }
</style>
