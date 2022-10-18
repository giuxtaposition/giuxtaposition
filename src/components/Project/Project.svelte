<script lang="ts">
    import type { Project } from "src/types/Project"

    export let project: Project
</script>

<li class="project">
    <div class="project-content">
        <div>
            <h3 class="project-title">
                <a href={project.url} rel="noopener noreferrer" target="_blank"
                    >{project.title}</a
                >
            </h3>
            <div class="project-description">
                <p>
                    {project.description}
                </p>
            </div>
            <ul class="project-tech-list">
                {#each project.techList as tech}
                    <li>{tech}</li>
                {/each}
            </ul>
            <div class="project-links">
                <a
                    href={project.githubUrl}
                    aria-label="GitHub Link"
                    rel="noopener noreferrer"
                    target="_blank"
                    ><svg
                        xmlns="http://www.w3.org/2000/svg"
                        role="img"
                        viewBox="0 0 24 24"
                        fill="none"
                        stroke="currentColor"
                        stroke-width="2"
                        stroke-linecap="round"
                        stroke-linejoin="round"
                        class="feather feather-github"
                        ><title>GitHub</title><path
                            d="M9 19c-5 1.5-5-2.5-7-3m14 6v-3.87a3.37 3.37 0 0 0-.94-2.61c3.14-.35 6.44-1.54 6.44-7A5.44 5.44 0 0 0 20 4.77 5.07 5.07 0 0 0 19.91 1S18.73.65 16 2.48a13.38 13.38 0 0 0-7 0C6.27.65 5.09 1 5.09 1A5.07 5.07 0 0 0 5 4.77a5.44 5.44 0 0 0-1.5 3.78c0 5.42 3.3 6.61 6.44 7A3.37 3.37 0 0 0 9 18.13V22"
                        /></svg
                    ></a
                ><a
                    href={project.url}
                    aria-label="External Link"
                    class="external"
                    rel="noopener noreferrer"
                    target="_blank"
                    ><svg
                        xmlns="http://www.w3.org/2000/svg"
                        role="img"
                        viewBox="0 0 24 24"
                        fill="none"
                        stroke="currentColor"
                        stroke-width="2"
                        stroke-linecap="round"
                        stroke-linejoin="round"
                        class="feather feather-external-link"
                        ><title>External Link</title><path
                            d="M18 13v6a2 2 0 0 1-2 2H5a2 2 0 0 1-2-2V8a2 2 0 0 1 2-2h6"
                        /><polyline points="15 3 21 3 21 9" /><line
                            x1="10"
                            y1="14"
                            x2="21"
                            y2="3"
                        /></svg
                    ></a
                >
            </div>
        </div>
    </div>
    <div class="project-image">
        <a href={project.url} rel="noopener noreferrer" target="_blank"
            ><div class="img">
                <div
                    style="max-width: 700px;
                display: block;"
                >
                    <img
                        alt=""
                        role="presentation"
                        aria-hidden="true"
                        src="data:image/svg+xml;charset=utf-8,%3Csvg height='438' width='700' xmlns='http://www.w3.org/2000/svg' version='1.1'%3E%3C/svg%3E"
                        style="max-width: 100%; display: block; position: static;"
                    />
                </div>
                <img src={project.image} alt={project.title} />
            </div></a
        >
    </div>
</li>

<style>
    .project {
        position: relative;
        display: grid;
        gap: 10px;
        grid-template-columns: repeat(12, 1fr);
        -moz-box-align: center;
        align-items: center;
    }

    .project-title {
        font-size: clamp(24px, 5vw, 28px);
    }

    .project-description {
        box-shadow: 0 10px 30px -15px rgba(2, 12, 27, 0.7);
        transition: var(--transition);
        position: relative;
        z-index: 2;
        padding: 25px;
        border-radius: 4px;
        background-color: var(--dark-brand);
        color: var(--grey);
        white-space: pre-line;
    }

    .project-tech-list {
        display: flex;
        flex-wrap: wrap;
        position: relative;
        z-index: 2;
        margin: 25px 0px 10px;
        padding: 0px;
        list-style: none;
    }

    .project-tech-list li {
        margin: 0px 20px 5px 0px;
        color: var(--grey);
        font-family: var(--font-mono);
        font-size: 0.9rem;
        white-space: nowrap;
    }

    .project-links {
        display: flex;
        -moz-box-align: center;
        align-items: center;
        position: relative;
        margin-top: 10px;
        margin-left: -10px;
        color: var(--grey);
    }

    .project-links a svg {
        width: 20px;
        height: 20px;
    }

    .project-links a {
        display: flex;
        -moz-box-pack: center;
        justify-content: center;
        -moz-box-align: center;
        align-items: center;
        padding: 10px;
    }

    .project-image {
        box-shadow: 0 10px 30px -15px var(--dark-brand);
        transition: var(--transition);
        grid-area: 1 / 6 / -1 / -1;
        grid-column-start: 6;
        grid-column-end: -1;
        position: relative;
        z-index: 1;
    }

    .project-image a {
        width: 100%;
        height: 100%;
        background-color: var(--brand);
        border-radius: 4px;
        vertical-align: middle;
    }

    .project-image .img {
        border-radius: 4px;
        mix-blend-mode: multiply;
        filter: grayscale(100%) contrast(1) brightness(90%);
    }

    .img img {
        bottom: 0;
        height: 100%;
        left: 0;
        margin: 0;
        max-width: none;
        padding: 0;
        position: absolute;
        right: 0;
        top: 0;
        width: 100%;
    }

    .project-image a::before {
        content: "";
        position: absolute;
        width: 100%;
        height: 100%;
        inset: 0px;
        z-index: 3;
        transition: var(--transition);
        background-color: var(--dark-brand);
        mix-blend-mode: screen;
    }

    .project-image a:hover,
    .project-image a:focus {
        background: transparent;
        outline: currentcolor none 0px;
    }

    .project-image a:hover::before,
    .project-image a:focus::before,
    .project-image a:hover .img,
    .project-image a:focus .img {
        filter: none;
        background: transparent;
    }
</style>
