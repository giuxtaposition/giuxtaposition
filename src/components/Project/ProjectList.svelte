<script lang="ts">
    import type { Project as ProjectType } from "src/types/Project"
    import Project from "./Project.svelte"
    export let projects: ProjectType[]
</script>

<ul class="projectList-container">
    {#each projects as project, i}
        <Project {project} />
    {/each}
</ul>

<style>
    .projectList-container {
        display: flex;
        flex-direction: column;
        gap: 3rem;
    }

    :global(.project:nth-of-type(2n + 1) .project-content) {
        grid-column: 7 / -1;
        text-align: right;
    }

    :global(.project .project-content) {
        position: relative;
        grid-area: 1 / 1 / -1 / 7;
        grid-column-start: 1;
        grid-column-end: 7;
    }

    :global(.project:nth-of-type(2n + 1) .project-tech-list) {
        justify-content: flex-end;
    }

    :global(.project:nth-of-type(2n + 1) .project-links) {
        -moz-box-pack: end;
        justify-content: flex-end;
        margin-left: 0px;
        margin-right: -10px;
    }

    :global(.project:nth-of-type(2n + 1) .project-image) {
        grid-column: 1 / 8;
    }
</style>
