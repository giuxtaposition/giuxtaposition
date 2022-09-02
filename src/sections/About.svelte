<section id="about">
    <h2 class="numbered-heading">About Me</h2>
    <div class="inner">
        <div>
            <div>
                <p>
                    Hello! My name is Giulia and I enjoy making things that live
                    on the internet. <br /> My interest in web development started
                    back when I was in middle school and I decided to try to make
                    my own RPG dedicated forum. I learned the basics of HTML & CSS
                    and tried to make it as pretty as I could, which was not much!
                </p>
                <p>
                    Since then I've been very passionate about everything
                    <span>Frontend</span>.
                </p>
                <p>
                    These days I've been working at <a
                        target="_blank"
                        rel="noreferrer"
                        href="https://www.claranet.it/">Claranet Italia</a
                    >, learning more about the backend world and trying to write
                    code I'm proud of.
                </p>
                <p>
                    Here are a few technologies I’ve been working with recently:
                </p>
            </div>
            <ul class="skills-list">
                <li>JavaScript (ES6+)</li>
                <li>TypeScript</li>
                <li>React</li>
                <li>Node.js</li>
                <li>Rust</li>
                <li>Elm</li>
            </ul>
        </div>
        <div id="about-photo">
            <img alt="decoration" src="/decoration.svg" />

            <div class="image-container"><img alt="me" src="/photo.png" /></div>
        </div>
    </div>
</section>

<style>
    #about {
        color: var(--grey);
    }
    #about .inner {
        display: grid;
        grid-template-columns: 3fr 2fr;
        gap: 50px;
    }

    #about-photo {
        display: flex;
        align-items: center;
        justify-content: center;
        position: relative;
        max-width: 350px;
        min-width: 350px;
    }

    #about-photo img[alt="decoration"] {
        left: 15rem;
    }
    #about-photo img[alt="me"] {
        width: 350px;
        height: 350px;
        border-radius: 50%;
        object-fit: cover;
    }

    #about a {
        color: var(--brand);
    }

    .image-container {
        display: inline-block;
        position: relative;
        line-height: 0;
        background: #ffffff;
        border-radius: 50%;
    }
    .image-container::after {
        content: "";
        position: absolute;
        width: 100%;
        height: 100%;
        top: 0;
        left: 0;
        mix-blend-mode: multiply;
        background: #fa00cc;
        opacity: 0.15;
    }
    .image-container > img {
        -webkit-filter: contrast(128%) grayscale(0%) hue-rotate(0deg) invert(0%)
            opacity(100%) saturate(120%) sepia(0%);
        filter: contrast(128%) grayscale(0%) hue-rotate(0deg) invert(0%)
            opacity(100%) saturate(120%) sepia(0%);
        mix-blend-mode: none;
    }

    .skills-list {
        display: grid;
        grid-template-columns: repeat(2, minmax(140px, 200px));
        gap: 0px 10px;
        padding: 0px;
        margin: 20px 0px 0px;
        overflow: hidden;
        list-style: none;
    }

    .skills-list li {
        position: relative;
        margin-bottom: 10px;
        padding-left: 20px;
        font-size: 13px;
        font-family: "SF Mono", monospace;
    }

    .skills-list li::before {
        content: "▹";
        position: absolute;
        left: 0px;
        color: var(--brand);
        font-size: 14px;
        line-height: 12px;
    }

    span {
        color: var(--brand);
    }
</style>
