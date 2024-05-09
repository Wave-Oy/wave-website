<script lang="ts">
    import '$lib/styles/app.css';
    import Navbar from '$lib/components/Navbar.svelte';
    import Footer from '$lib/components/Footer.svelte';
    // document.getElementById('').src = imgUrl
</script>

<Navbar />
<main id="back">
    <slot />
</main>
<Footer />

<style lang="scss">
    main {
        margin: 0;
        padding: 0;
        height: 100%;
        width: 100vw;
    }
</style>