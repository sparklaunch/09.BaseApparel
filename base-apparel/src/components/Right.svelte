<script lang="ts">
    let innerWidth: number;
    $: isMobile = innerWidth <= 1440;
</script>

<svelte:window bind:innerWidth />
<div id="right">
    {#if isMobile}
        <img src="/assets/logo.svg" alt="Logo" />
    {/if}
    <img src="/assets/hero-{isMobile ? 'mobile' : 'desktop'}.jpg" alt="Hero" />
</div>

<style>
    #right {
        width: 45%;
    }
    #right > img {
        height: 100%;
        display: block;
    }
    @media all and (max-width: 1440px) {
        #right {
            width: 100%;
        }
        #right > img:first-child {
            margin: 30px;
        }
        #right > img:last-child {
            width: 100%;
            height: auto;
        }
    }
</style>
