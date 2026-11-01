<script setup lang="ts">
import Navbar from '@/components/Navbar.vue'
</script>

<template>
    <Navbar />

    <main class="thanks">
        <div class="container">
            <section class="card">
                <div class="success-icon" aria-hidden="true">
                    ✓
                </div>

                <span class="eyebrow">MESSAGE SENT</span>

                <h1>Thank you for reaching out<span>.</span></h1>

                <p class="message">
                    Your message means a lot to me!
                    I'll get back to you as soon as possible.
                </p>

                <router-link to="/" class="btn">
                    <span aria-hidden="true">←</span>
                    Back to home
                </router-link>

                <p class="signature">
                    Until then, have a lovely day.
                </p>
            </section>
        </div>
    </main>
</template>

<style scoped>
.thanks {
    --background: #f4f1de;
    --coral: #c96851;
    --coral-dark: #ad503d;
    --text: #292820;
    --muted: #68665d;
    --card: #fffdf7;
    --border: #e5deca;

    box-sizing: border-box;
    display: flex;
    align-items: center;
    justify-content: center;
    min-height: 100vh;
    padding: 7rem 1.5rem 3rem;
    background: var(--background);
    color: var(--text);
}

.container {
    width: 100%;
    max-width: 700px;
    margin: 0 auto;
}

.card {
    position: relative;
    overflow: hidden;
    padding: clamp(2.5rem, 7vw, 5rem) clamp(1.5rem, 5vw, 4rem);
    border: 1px solid var(--border);
    border-radius: 24px;
    background: var(--card);
    text-align: center;
    box-shadow: 0 16px 45px rgba(54, 43, 27, 0.06);
}

.card::before {
    position: absolute;
    top: 0;
    left: 0;
    width: 100%;
    height: 5px;
    background: var(--coral);
    content: '';
}

.success-icon {
    display: grid;
    place-items: center;
    width: 68px;
    height: 68px;
    margin: 0 auto 1.8rem;
    border: 1px solid rgba(201, 104, 81, 0.2);
    border-radius: 50%;
    background: #f3e5dc;
    color: var(--coral-dark);
    font-size: 2rem;
    font-weight: 600;
}

.eyebrow {
    color: var(--coral);
    font-size: 0.75rem;
    font-weight: 700;
    letter-spacing: 0.16em;
}

.card h1 {
    max-width: 540px;
    margin: 1rem auto;
    font-size: clamp(2rem, 5vw, 3.2rem);
    line-height: 1.15;
    letter-spacing: -0.05em;
}

.card h1 span {
    color: var(--coral);
}

.message {
    max-width: 440px;
    margin: 0 auto 2rem;
    color: var(--muted);
    font-size: 1.05rem;
    line-height: 1.8;
}

.btn {
    display: inline-flex;
    align-items: center;
    justify-content: center;
    gap: 0.7rem;
    padding: 0.9rem 1.5rem;
    border: 1px solid var(--coral);
    border-radius: 10px;
    background: var(--coral);
    color: #fffdf7;
    font-weight: 600;
    text-decoration: none;
    transition: background 0.2s ease, transform 0.2s ease;
}

.btn:hover {
    transform: translateY(-2px);
    background: var(--coral-dark);
}

.btn:focus-visible {
    outline: 3px solid rgba(201, 104, 81, 0.4);
    outline-offset: 4px;
}

.signature {
    margin: 2rem 0 0;
    color: var(--muted);
    font-size: 0.85rem;
}

@media (max-width: 600px) {
    .thanks {
        padding: 6.5rem 1rem 2rem;
    }

    .card {
        border-radius: 18px;
    }
}

@media (prefers-reduced-motion: reduce) {
    .btn {
        transition: none;
    }
}
</style>
