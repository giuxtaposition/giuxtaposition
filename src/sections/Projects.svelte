<script lang="ts">
    import { onMount } from "svelte"
    import ProjectList from "../components/Project/ProjectList.svelte"
    import type { Project } from "../types/Project"

    let projects: Project[] = []

    onMount(async () => {
        const apiResponse = await fetch("/data/projects/projects.json")
        projects = await apiResponse.json()
    })
</script>

<section id="projects">
    <h2 class="numbered-heading">What I built</h2>
    <ProjectList {projects} />
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
