<script lang="ts">
    import Left from "./components/Left.svelte";
    import Right from "./components/Right.svelte";
</script>

<svelte:head>
    <link rel="preconnect" href="https://fonts.googleapis.com" />
    <link rel="preconnect" href="https://fonts.gstatic.com" />
    <link
        href="https://fonts.googleapis.com/css2?family=Josefin+Sans:wght@300;400;600&display=swap"
        rel="stylesheet"
    />
</svelte:head>
<main>
    <Left />
    <Right />
</main>

<style>
    main {
        display: flex;
        height: 100%;
    }
</style>
