<script lang="ts">
    import { fade } from "svelte/transition"
    import type { Job } from "src/types/Job"

    export let jobs: Job[]
    let isSelected: number = 0

    const changeSelected = (number: number) => {
        isSelected = number
    }
</script>

<div class="tablist-container">
    <div role="tablist" aria-label="Job tabs">
        {#each jobs as job, i}
            <button
                class={isSelected === i ? "active" : ""}
                id={`tab-${i}`}
                role="tab"
                tabindex={i}
                on:click={() => changeSelected(i)}
                aria-selected={isSelected === i}
                aria-controls={`panel-${i}`}><span>{job.company}</span></button
            >
        {/each}
    </div>
    <div class="tab-highlight" />
    <div class="tab-panels">
        {#each jobs as job, i}
            {#if isSelected === i}
                <div
                    id={`panel-${i}`}
                    role="tabpanel"
                    tabindex={i}
                    aria-labelledby={`tab-${i}`}
                    aria-hidden={isSelected === i}
                    out:fade={{ duration: 200 }}
                    in:fade={{ delay: 250 }}
                >
                    <h3>
                        <span>{job.role}</span><span class="company"
                            >&nbsp;@&nbsp;<span class="highlight"
                                >{job.company}</span
                            ></span
                        >
                    </h3>
                    <p class="range">{job.date}</p>
                    <div>
                        <ul>
                            {#each job.description as description, i}
                                <li>{description}</li>
                            {/each}
                        </ul>
                    </div>
                </div>
            {/if}
        {/each}
    </div>
</div>

<style>
    .tablist-container {
        display: flex;
        min-height: 340px;
    }

    div[role="tablist"] {
        padding: 0px;
        width: max-content;
        z-index: 3;
        margin-top: 5rem;
        list-style: none;
        position: relative;
    }

    button[role="tab"] {
        text-decoration: none;
        text-decoration-skip-ink: auto;
        position: relative;
        transition: all 0.25s cubic-bezier(0.645, 0.045, 0.355, 1);
        display: flex;
        align-items: center;
        width: 100%;
        height: 42px;
        padding: 0px 20px 2px;
        border-left: 2px solid var(--dark-brand);
        background-color: transparent;
        color: var(--grey);
        font-family: var(--font-mono);
        font-size: 13px;
        text-align: left;
        white-space: nowrap;
        border-radius: 0px;
    }

    button[role="tab"]:hover,
    button.active {
        background-color: var(--hover-dark);
    }

    button[role="tab"] span {
        text-decoration-skip-ink: auto;
        text-align: left;
        white-space: nowrap;
    }
    button[role="tab"]:hover span,
    button.active span {
        color: var(--brand);
    }

    .tab-panels {
        margin-left: 20px;
        width: 100%;
    }

    div[role="tabpanel"] {
        height: auto;
        width: 100%;
        padding: 10px 5px;
    }

    div[role="tabpanel"] h3 {
        margin-bottom: 2px;
        font-size: 1.4rem;
        font-weight: 500;
        line-height: 1.3;
    }

    div[role="tabpanel"] .range {
        margin-bottom: 25px;
        color: var(--grey);
        font-family: var(--font-mono);
        font-size: 0.9rem;
    }

    ul {
        padding: 0px;
        margin: 0px;
        list-style: none;
        font-size: 1rem;
    }

    li {
        position: relative;
        padding-left: 30px;
        margin-bottom: 10px;
    }

    ul li::before {
        content: "▹";
        position: absolute;
        left: 0px;
        color: var(--brand);
    }
</style>
