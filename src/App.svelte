<script lang="ts">
    import Experience from "./sections/Experience.svelte"
    import About from "./sections/About.svelte"
    import Hero from "./sections/Hero.svelte"
    import Navbar from "./sections/Navbar.svelte"
</script>

<Navbar />

<main>
    <Hero />
    <About />
    <Experience />
</main>

<style>
    main {
        flex-direction: column;
        justify-content: center;
        display: flex;
    }
</style>
