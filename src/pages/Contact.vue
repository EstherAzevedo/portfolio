<script setup lang="ts">
import Navbar from '@/components/Navbar.vue';
</script>

<template>
    <Navbar />

    <main class="contact">
        <div class="container">
            <header class="contact-header">
                <span class="eyebrow">LET'S CONNECT</span>
                <h1>Get in touch<span>.</span></h1>
                <p class="subtitle">
                    Have a project in mind, a question, or just want to say hello?
                    I'd love to hear from you.
                </p>
            </header>

            <div class="contact-card">
                <section class="contact-form-section">
                    <h2>Send me a message</h2>
                    <p class="form-description">
                        Fill out the form below and I'll get back to you as soon as possible.
                    </p>

                    <form action="https://formsubmit.co/0459f374ca63b416fb4baf017a21b45d" method="POST">
                        <input type="hidden" name="_next" value="https://estherazevedo.github.io/portfolio/#/thanks" />
                        <input type="hidden" name="_captcha" value="false" />
                        <input type="hidden" name="_subject" value="New contact from portfolio" />

                        <label for="name">Name</label>
                        <input id="name" type="text" name="name" placeholder="Your name" autocomplete="name" required />

                        <label for="email">Email</label>
                        <input id="email" type="email" name="email" placeholder="you@example.com" autocomplete="email"
                            required />

                        <label for="message">Message</label>
                        <textarea id="message" name="message" placeholder="Tell me what's on your mind..." rows="5"
                            required></textarea>

                        <button type="submit">
                            Send message
                            <span aria-hidden="true">↗</span>
                        </button>
                    </form>
                </section>

                <aside class="contact-aside">
                    <div class="aside-decoration" aria-hidden="true">✳</div>

                    <span class="aside-label">ELSEWHERE ON THE WEB</span>
                    <h2>Let's connect<br />beyond the inbox.</h2>
                    <p>
                        You can also find me on these platforms to follow my work
                        and explore my projects.
                    </p>

                    <div class="social-links">
                        <a href="https://github.com/EstherAzevedo" target="_blank" rel="noopener noreferrer"
                            class="social-link">
                            <span class="social-icon" aria-hidden="true">GH</span>
                            <span>
                                <strong>GitHub</strong>
                                <small>Explore my projects</small>
                            </span>
                            <span class="arrow" aria-hidden="true">↗</span>
                        </a>

                        <a href="https://www.linkedin.com/in/esther-azevedo-aguiar/" target="_blank"
                            rel="noopener noreferrer" class="social-link">
                            <span class="social-icon" aria-hidden="true">in</span>
                            <span>
                                <strong>LinkedIn</strong>
                                <small>Connect professionally</small>
                            </span>
                            <span class="arrow" aria-hidden="true">↗</span>
                        </a>

                        <a href="https://wa.me/5585991781234?text=Hello%20Esther!%20I%20found%20your%20portfolio."
                            target="_blank" rel="noopener noreferrer" class="social-link">
                            <span class="social-icon" aria-hidden="true">WA</span>
                            <span>
                                <strong>WhatsApp</strong>
                                <small>Send me a message</small>
                            </span>
                            <span class="arrow" aria-hidden="true">↗</span>
                        </a>
                    </div>

                    <div class="availability">
                        <span class="availability-dot"></span>
                        Open to new opportunities
                    </div>
                </aside>
            </div>
            <footer class="contact-footer">
                <span>&copy; 2026 Esther Azevedo</span>
            </footer>
        </div>
    </main>
</template>

<style scoped>
.contact {
    --background: #f4f1de;
    --coral: #c96851;
    --coral-dark: #ad503d;
    --text: #292820;
    --muted: #68665d;
    --card: #fffdf7;
    --border: #e5deca;

    min-height: 100vh;
    box-sizing: border-box;
    padding: 7.5rem 1.5rem 2rem;
    background: var(--background);
    color: var(--text);
}

.container {
    width: 100%;
    max-width: 1000px;
    margin: 0 auto;
}

.contact-header {
    max-width: 650px;
    margin-bottom: 2.5rem;
}

.eyebrow,
.aside-label {
    color: var(--coral);
    font-size: 0.75rem;
    font-weight: 700;
    letter-spacing: 0.16em;
}

.contact-header h1 {
    margin: 0.8rem 0 0.9rem;
    font-size: clamp(2.6rem, 6vw, 4.3rem);
    line-height: 1.05;
    letter-spacing: -0.055em;
}

.contact-header h1 span {
    color: var(--coral);
}

.subtitle {
    max-width: 530px;
    margin: 0;
    color: var(--muted);
    font-size: 1.05rem;
    line-height: 1.8;
}

.contact-card {
    display: grid;
    grid-template-columns: 1.1fr 0.9fr;
    overflow: hidden;
    background: var(--card);
    border: 1px solid var(--border);
    border-radius: 24px;
    box-shadow: 0 16px 45px rgba(54, 43, 27, 0.06);
}

.contact-form-section {
    padding: clamp(1.5rem, 4vw, 3rem);
}

.contact-form-section h2,
.contact-aside h2 {
    margin: 0;
    font-size: 1.65rem;
    letter-spacing: -0.035em;
}

.form-description {
    margin: 0.65rem 0 1.8rem;
    color: var(--muted);
    font-size: 0.93rem;
    line-height: 1.7;
}

form {
    display: flex;
    flex-direction: column;
    gap: 0.65rem;
}

form label {
    margin-top: 0.45rem;
    color: var(--text);
    font-size: 0.88rem;
    font-weight: 600;
}

input,
textarea {
    width: 100%;
    box-sizing: border-box;
    padding: 0.9rem 1rem;
    border: 1px solid var(--border);
    border-radius: 10px;
    outline: none;
    background: #fffefa;
    color: var(--text);
    font: inherit;
    font-size: 0.94rem;
    transition: border-color 0.2s ease, box-shadow 0.2s ease;
}

input::placeholder,
textarea::placeholder {
    color: #999487;
}

input:focus,
textarea:focus {
    border-color: var(--coral);
    box-shadow: 0 0 0 3px rgba(201, 104, 81, 0.12);
}

textarea {
    min-height: 125px;
    resize: vertical;
}

button {
    display: flex;
    align-items: center;
    justify-content: space-between;
    gap: 1rem;
    margin-top: 0.8rem;
    padding: 1rem 1.2rem;
    border: 1px solid var(--coral);
    border-radius: 10px;
    background: var(--coral);
    color: #fffdf7;
    font: inherit;
    font-weight: 600;
    cursor: pointer;
    transition: background 0.2s ease, transform 0.2s ease;
}

button:hover {
    background: var(--coral-dark);
    transform: translateY(-2px);
}

button:focus-visible,
.social-link:focus-visible {
    outline: 3px solid rgba(201, 104, 81, 0.45);
    outline-offset: 3px;
}

button span {
    font-size: 1.2rem;
}

.contact-aside {
    position: relative;
    overflow: hidden;
    padding: clamp(1.5rem, 4vw, 3rem);
    background: #f3e5dc;
    border-left: 1px solid var(--border);
}

.aside-decoration {
    position: absolute;
    top: -35px;
    right: 18px;
    color: rgba(201, 104, 81, 0.13);
    font-size: 9rem;
    line-height: 1;
    pointer-events: none;
}

.aside-label {
    display: block;
    margin-bottom: 1.2rem;
    font-size: 0.68rem;
}

.contact-aside h2 {
    position: relative;
    font-size: clamp(1.6rem, 3vw, 2rem);
    line-height: 1.3;
}

.contact-aside>p {
    margin: 1rem 0 1.8rem;
    color: var(--muted);
    font-size: 0.92rem;
    line-height: 1.8;
}

.social-links {
    display: flex;
    flex-direction: column;
    gap: 0.7rem;
}

.social-link {
    display: flex;
    align-items: center;
    gap: 0.85rem;
    padding: 0.9rem;
    border: 1px solid rgba(201, 104, 81, 0.15);
    border-radius: 12px;
    background: rgba(255, 253, 247, 0.7);
    color: var(--text);
    text-decoration: none;
    transition: border-color 0.2s ease, transform 0.2s ease,
        background 0.2s ease;
}

.social-link:hover {
    transform: translateX(3px);
    border-color: rgba(201, 104, 81, 0.5);
    background: var(--card);
}

.social-icon {
    display: grid;
    flex-shrink: 0;
    place-items: center;
    width: 40px;
    height: 40px;
    border-radius: 10px;
    background: #e5deca;
    color: var(--coral-dark);
    font-size: 0.85rem;
    font-weight: 800;
}

.social-link>span:nth-child(2) {
    display: flex;
    flex: 1;
    flex-direction: column;
    gap: 0.2rem;
}

.social-link strong {
    font-size: 0.9rem;
}

.social-link small {
    color: var(--muted);
    font-size: 0.78rem;
}

.arrow {
    color: var(--coral);
    font-size: 1.1rem;
}

.availability {
    display: flex;
    align-items: center;
    gap: 0.55rem;
    margin-top: 2rem;
    color: var(--muted);
    font-size: 0.8rem;
}

.availability-dot {
    width: 8px;
    height: 8px;
    border-radius: 50%;
    background: #66845b;
    box-shadow: 0 0 0 4px rgba(102, 132, 91, 0.12);
}

.contact-footer {
    display: flex;
    justify-content: center;
    gap: 1rem;
    margin-top: 1.5rem;
    color: var(--muted);
    font-size: 0.78rem;
}

@media (max-width: 760px) {
    .contact {
        padding: 6.5rem 1rem 1.5rem;
    }

    .contact-header {
        margin-bottom: 1.8rem;
    }

    .contact-card {
        grid-template-columns: 1fr;
        border-radius: 18px;
    }

    .contact-aside {
        border-top: 1px solid var(--border);
        border-left: none;
    }

    .contact-footer {
        flex-direction: column;
        gap: 0.4rem;
    }
}

@media (prefers-reduced-motion: reduce) {

    *,
    *::before,
    *::after {
        scroll-behavior: auto !important;
        transition-duration: 0.01ms !important;
        animation-duration: 0.01ms !important;
    }
}
</style>
