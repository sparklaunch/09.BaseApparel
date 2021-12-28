<script lang="ts">
    import Left from "./components/Left.svelte";
    import Right from "./components/Right.svelte";
    let windowHeight: number;
    let mainHeight: number;
    $: offset = windowHeight - mainHeight;
</script>

<svelte:head>
    <link rel="preconnect" href="https://fonts.googleapis.com" />
    <link rel="preconnect" href="https://fonts.gstatic.com" />
    <link
        href="https://fonts.googleapis.com/css2?family=Josefin+Sans:wght@300;400;600&display=swap"
        rel="stylesheet"
    />
</svelte:head>
<svelte:window bind:innerHeight={windowHeight} />
<main bind:clientHeight={mainHeight}>
    <Left {offset} />
    <Right />
</main>

<style>
    main {
        display: flex;
        height: 100%;
    }
    @media all and (max-width: 1440px) {
        main {
            flex-direction: column-reverse;
            height: auto;
        }
    }
</style>
