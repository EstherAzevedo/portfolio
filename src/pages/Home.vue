<script setup lang="ts">
import Navbar from '@/components/Navbar.vue'
</script>

<template>
    <div class="home">
        <Navbar />

        <main class="hero">
            <section class="content">
                <p class="eyebrow">SOFTWARE DEVELOPER</p>

                <h1>
                    Hello, I'm<br />
                    <span>Esther Azevedo.</span>
                </h1>

                <p class="description">
                    Information Systems graduate from the Federal University of Ceará
                    (UFC), passionate about building meaningful software solutions.
                    I'm interested in software development and Artificial Intelligence.
                </p>

                <div class="actions">
                    <RouterLink to="/projects" class="button primary">
                        Explore my work <span>↗</span>
                    </RouterLink>

                    <RouterLink to="/aboutme" class="button secondary">
                        More about me
                    </RouterLink>
                </div>

                <div class="socials">
                    <a href="https://github.com/SEU-USUARIO" target="_blank" rel="noopener noreferrer">
                        GitHub ↗
                    </a>

                    <a href="https://linkedin.com/in/SEU-USUARIO" target="_blank" rel="noopener noreferrer">
                        LinkedIn ↗
                    </a>
                </div>
            </section>

            <section class="visual">
                <div class="photo-frame">
                    <img src="/esther.jpeg" alt="Portrait of Esther Azevedo" />
                </div>

                <div class="photo-label">
                    <span class="dot"></span>
                    <span>Technology with purpose.</span>
                </div>
            </section>
        </main>
    </div>
</template>

<style scoped>
.home {
    min-height: 100vh;
    background: #f4f1de;
    color: #292820;
}

.hero {
    max-width: 1100px;
    min-height: 82vh;
    margin: 0 auto;
    padding: 64px 32px;
    display: flex;
    align-items: center;
    justify-content: space-between;
    gap: 64px;
}

.content {
    flex: 1;
    max-width: 590px;
}

.eyebrow {
    color: #b85f4b;
    font-size: 0.78rem;
    font-weight: 700;
    letter-spacing: 2.5px;
}

h1 {
    margin: 24px 0;
    font-size: clamp(3rem, 5.5vw, 5rem);
    line-height: 1.08;
    letter-spacing: -2.5px;
}

h1 span {
    color: #c96851;
}

.description {
    max-width: 500px;
    color: #68665d;
    font-size: 1.05rem;
    line-height: 1.9;
}

.actions {
    display: flex;
    flex-wrap: wrap;
    gap: 14px;
    margin-top: 32px;
}

.button {
    display: inline-flex;
    align-items: center;
    gap: 12px;
    padding: 14px 20px;
    border-radius: 6px;
    text-decoration: none;
    font-size: 0.92rem;
    font-weight: 600;
    transition: transform 0.2s, background 0.2s;
}

.button:hover {
    transform: translateY(-2px);
}

.primary {
    background: #c96851;
    color: white;
}

.primary:hover {
    background: #ad523e;
}

.secondary {
    border: 1px solid #d5cdb7;
    color: #39372f;
}

.secondary:hover {
    background: #ebe5d1;
}

.socials {
    display: flex;
    gap: 24px;
    margin-top: 34px;
}

.socials a {
    color: #68665d;
    font-size: 0.9rem;
    text-decoration: none;
}

.socials a:hover {
    color: #c96851;
}

.visual {
    flex-shrink: 0;
    width: 340px;
}

.photo-frame {
    position: relative;
    padding: 10px;
    background: #e7dfc8;
    border-radius: 170px 170px 12px 12px;
    box-shadow: 14px 14px 0 #e8c4b3;
}

.photo-frame img {
    display: block;
    width: 100%;
    height: 420px;
    object-fit: cover;
    object-position: center 35%;
    border-radius: 160px 160px 7px 7px;
}

.photo-label {
    display: flex;
    align-items: center;
    justify-content: center;
    gap: 9px;
    margin-top: 28px;
    color: #68665d;
    font-size: 0.85rem;
}

.dot {
    width: 8px;
    height: 8px;
    border-radius: 50%;
    background: #c96851;
}

@media (max-width: 800px) {
    .hero {
        min-height: auto;
        padding: 48px 24px 56px;
        flex-direction: column-reverse;
        align-items: stretch;
        gap: 44px;
    }

    .visual {
        width: min(280px, 80%);
        margin: 0 auto;
    }

    .photo-frame img {
        height: 340px;
    }

    h1 {
        font-size: clamp(2.8rem, 10vw, 4rem);
        letter-spacing: -1.5px;
    }

    .description {
        font-size: 1rem;
    }
}

@media (prefers-reduced-motion: reduce) {
    .button {
        transition: none;
    }
}
</style>
