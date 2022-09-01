<script>
    import FaGithub from "svelte-icons/fa/FaGithub.svelte"
    import FaLinkedin from "svelte-icons/fa/FaLinkedin.svelte"
    import MdEmail from "svelte-icons/md/MdEmail.svelte"
</script>

<div class="hero">
    <div class="hero-header">
        <div>
            <img alt="decoration" src="/decoration.svg" />
            <p class="hello">Hello! I'm-</p>
        </div>
        <h1>Giulia Ye.</h1>
    </div>
    <div>
        <h2>
            <span>Full Stack Developer.</span> With a passion for learning
            <br />and software craftsmanship.
        </h2>
    </div>
    <div>
        <p>
            🚀 Trying to understand functional programming.
            <br />
            💻 Currently working at
            <a target="_blank" rel="noreferrer" href="https://www.claranet.it/"
                >Claranet Italia</a
            >.
        </p>
    </div>
    <br />
    <div class="links">
        <a
            target="_blank"
            rel="noopener noreferrer"
            href="https://github.com/giuxtaposition"
            ><button type="button"
                ><div class="icon"><FaGithub /></div>
                Github</button
            ></a
        ><a
            target="_blank"
            rel="noopener noreferrer"
            href="https://linkedin.com/in/giulia-ye-6a0004247/"
            ><button type="button"
                ><div class="icon"><FaLinkedin /></div>
                LinkedIn</button
            ></a
        ><a
            target="_blank"
            rel="noopener noreferrer"
            href="mailto:yg97.cs@gmail.com"
            ><button type="button"
                ><div class="icon"><MdEmail /></div>
                Email</button
            ></a
        >
    </div>
</div>

<style>
    .hero {
        padding-inline-start: 10vw;
        padding-inline-end: 10vw;
        margin-top: 22.5vh;
    }

    .hero-header {
        line-height: 0;
    }

    .hero img {
        width: 150px;
        top: -15px;
        left: calc(2.5rem * -1);
        filter: invert(0.1);
        position: absolute;
        z-index: -1;
        max-width: 100%;
        height: auto;
    }

    .hero p {
        color: var(--grey);
        font-size: 1.25rem;
    }

    .hero p a {
        color: var(--brand);
    }

    .hero p.hello {
        position: relative;
        color: var(--brand);
        font-size: 2rem;
        font-weight: 600;
    }

    .hero-header div {
        position: relative;
    }

    .hero h1 {
        font-size: 7rem;
        font-weight: 700;
    }

    .hero h2 {
        line-height: 1.2;
        font-weight: 600;
        font-size: 2rem;
        letter-spacing: -1.6px;
        color: var(--grey);
    }

    .hero h2 span {
        color: var(--white);
    }

    .links {
        display: flex;
        gap: 1rem;
    }

    .icon {
        width: 16px;
        height: 16px;
        color: var(--brand);
        margin-right: 0.25rem;
    }
</style>
