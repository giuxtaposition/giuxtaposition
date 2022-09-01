<script lang="ts">
    import Hero from "./components/Hero.svelte"
    import Navbar from "./components/Navbar.svelte"
</script>

<Navbar />

<main>
    <Hero />
</main>

<style>
    main {
        flex-direction: column;
        display: flex;
    }
</style>
