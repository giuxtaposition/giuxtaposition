<script lang="ts">
    import About from "./components/About.svelte"
    import Hero from "./components/Hero.svelte"
    import Navbar from "./components/Navbar.svelte"
</script>

<Navbar />

<main>
    <Hero />
    <About />
</main>

<style>
    main {
        flex-direction: column;
        display: flex;
    }
</style>
