<div class="nav-container">
    <nav>
        <div class="logo" tabindex="-1">
            <a href="/" aria-label="home"
                ><img src="/logo.svg" alt="logo" /><span>&#123;</span>Giulia Ye<span
                    >&#125;</span
                ></a
            >
        </div>
        <div>
            <ol>
                <li><a href="/#about">About</a></li>
                <li><a href="/#experience">Experience</a></li>
                <li><a href="/#projects">Projects</a></li>
            </ol>
        </div>
    </nav>
</div>

<style>
    .nav-container {
        position: fixed;
        top: 0px;
        left: 0px;
        right: 0px;
        max-width: 100vw;
        border-bottom: 0.5px solid #1e2029;
        background-color: var(--dark-background-color);
        z-index: 2;
    }
    nav {
        display: flex;
        justify-content: space-between;
        align-items: center;
        font-size: 1rem;
        padding-inline-start: 3vw;
        padding-inline-end: 3vw;
        padding-top: 0.75rem;
        padding-bottom: 0.75rem;
    }
    ol {
        display: flex;
        -moz-box-pack: justify;
        justify-content: space-between;
        -moz-box-align: center;
        align-items: center;
        padding: 0px;
        margin: 0px;
        list-style: none;
    }
    ol li {
        margin: 0 1rem;
        counter-increment: item 1;
    }
    ol li a::before {
        content: "0" counter(item) ".";
        margin-right: 5px;
        color: var(--brand);
        font-size: 0.9rem;
        text-align: right;
    }
    .logo img {
        width: 30px;
        height: 30px;
        margin-right: 0.5rem;
    }
    .logo a {
        font-size: 32px;
        font-weight: 700;
    }
    .logo span {
        font-weight: 600;
        color: #8f9094;
    }
</style>
