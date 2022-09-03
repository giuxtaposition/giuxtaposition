<script lang="ts">
    import Tablist from "../components/Tablist/Tablist.svelte"
    import { onMount } from "svelte"
    import type { Job } from "../types/Job"

    let jobs: Job[] = []

    onMount(async () => {
        const apiResponse = await fetch("/data/jobs.json")
        jobs = await apiResponse.json()
    })
</script>

<section id="experience">
    <h2 class="numbered-heading">Where I’ve Worked</h2>
    <Tablist {jobs} />
</section>

<style>
    section {
        max-width: 60rem;
        opacity: 1;
        transform: matrix3d(1, 0, 0, 0, 0, 1, 0, 0, 0, 0, 1, 0, 0, 0, 0, 1);
        transition: opacity 0.5s cubic-bezier(0.645, 0.045, 0.355, 1) 0.2s,
            transform 0.5s cubic-bezier(0.645, 0.045, 0.355, 1) 0.2s;
    }
</style>
