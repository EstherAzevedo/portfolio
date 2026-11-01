<script setup lang="ts">
import Navbar from '@/components/Navbar.vue'

interface Education {
    degree: string
    institution: string
    period: string
    link?: string
    linkLabel?: string
}

const tccUrl = 'https://repositorio.ufc.br/handle/riufc/85783'
const diplomaUrl = 'ADD_GOOGLE_DRIVE_DIPLOMA_URL_HERE'

const education: Education[] = [
    {
        degree: 'Information Systems',
        institution: 'Federal University of Ceará (UFC)',
        period: '2020 – 2025',
        link: tccUrl,
        linkLabel: 'Read my undergraduate thesis'
    },
    {
        degree: 'Computer Technician',
        institution: 'Federal Institute of Education, Science and Technology of Ceará (IFCE)',
        period: '2018 – 2022',
        link: diplomaUrl,
        linkLabel: 'View technical diploma'
    }
]

const interests = [
    'Software Development',
    'Artificial Intelligence',
    'Web Development',
    'Mobile Development',
    'Technology in Education',
    'Reading',
    'Writing',
    'Open Source'
]
</script>

<template>
    <Navbar />

    <main class="about">
        <div class="container">
            <header class="page-heading">
                <h1>About Me<span>.</span></h1>
            </header>

            <section class="profile">
                <div class="about-photo">
                    <img src="/Esther_AboutMe.jpeg" alt="Portrait of Esther Azevedo" />
                </div>

                <div class="hero-text">
                    <p class="intro-label">Hello, I'm Esther!</p>

                    <h2>
                        Software developer with a passion for
                        <span>learning and creating.</span>
                    </h2>

                    <p class="intro">
                        I'm an Information Systems graduate from the Federal University
                        of Ceará (UFC), interested in building useful software solutions
                        and exploring new technologies.
                    </p>

                    <p class="intro">
                        My academic journey also sparked my interest in Artificial
                        Intelligence and its applications in education. Outside
                        technology, I enjoy reading and writing, activities that inspire
                        my curiosity and creativity.
                    </p>
                </div>
            </section>

            <section class="section">
                <div class="section-heading">
                    <span class="section-number">01</span>
                    <div>
                        <h2>Education</h2>
                        <p class="section-subtitle">
                            The academic journey behind my work.
                        </p>
                    </div>
                </div>

                <div class="education-list">
                    <article v-for="(edu, index) in education" :key="edu.degree" class="education-item">
                        <div class="education-marker">
                            {{ index === 0 ? '01' : '02' }}
                        </div>

                        <div class="education-content">
                            <p class="period">{{ edu.period }}</p>
                            <h3>{{ edu.degree }}</h3>
                            <p class="institution">{{ edu.institution }}</p>

                            <a v-if="edu.link" :href="edu.link" target="_blank" rel="noopener noreferrer"
                                class="document-link">
                                {{ edu.linkLabel }}
                                <span aria-hidden="true">↗</span>
                            </a>
                        </div>
                    </article>
                </div>
            </section>

            <section class="section interests-section">
                <div class="section-heading">
                    <span class="section-number">02</span>
                    <div>
                        <h2>Interests</h2>
                        <p class="section-subtitle">
                            Topics that inspire me to keep exploring.
                        </p>
                    </div>
                </div>

                <div class="interests-list">
                    <span v-for="interest in interests" :key="interest" class="interest-tag">
                        {{ interest }}
                    </span>
                </div>
            </section>
        </div>
    </main>
</template>

<style scoped>
.about {
    min-height: 100vh;
    padding: 4rem 2rem;
    background: #f4f1de;
    color: #292820;
}

.container {
    max-width: 1050px;
    margin: 0 auto;
}

.page-heading {
    margin-bottom: 2.5rem;
}

.eyebrow {
    margin: 0 0 0.8rem;
    color: #b85f4b;
    font-size: 0.75rem;
    font-weight: 700;
    letter-spacing: 2.5px;
}

.page-heading h1 {
    margin: 1rem;
    font-size: clamp(2.8rem, 6vw, 4rem);
    line-height: 1.1;
    letter-spacing: -2px;
}

.page-heading h1 span {
    color: #c96851;
}

.profile {
    display: grid;
    grid-template-columns: 290px minmax(0, 1fr);
    align-items: center;
    gap: 3rem;
    margin-bottom: 4rem;
}

.about-photo {
    padding: 9px;
    background: #e8dfca;
    border-radius: 150px 150px 10px 10px;
    box-shadow: 9px 9px 0 #e8c4b3;
}

.about-photo img {
    display: block;
    width: 100%;
    height: 350px;
    object-fit: cover;
    object-position: center 30%;
    border-radius: 145px 145px 5px 5px;
}

.hero-text {
    max-width: 620px;
}

.intro-label {
    margin: 0 0 0.8rem;
    color: #b85f4b;
    font-size: 0.9rem;
    font-weight: 700;
}

.hero-text h2 {
    margin: 0 0 1.25rem;
    font-size: clamp(1.8rem, 3.5vw, 2.5rem);
    line-height: 1.25;
    letter-spacing: -0.8px;
}

.hero-text h2 span {
    color: #c96851;
}

.intro {
    margin: 0 0 1rem;
    color: #68665d;
    font-size: 1rem;
    line-height: 1.85;
}

.section {
    margin-top: 2rem;
    padding: 2rem;
    background: #fffdf6;
    border: 1px solid #e5deca;
    border-radius: 12px;
}

.section-heading {
    display: flex;
    align-items: flex-start;
    gap: 1rem;
    margin-bottom: 2rem;
}

.section-number {
    padding-top: 0.35rem;
    color: #c96851;
    font-size: 0.8rem;
    font-weight: 700;
    letter-spacing: 1px;
}

.section-heading h2 {
    margin: 0;
    font-size: 1.7rem;
    letter-spacing: -0.5px;
}

.section-subtitle {
    margin: 0.45rem 0 0;
    color: #777368;
    font-size: 0.95rem;
    line-height: 1.6;
}

.education-list {
    display: flex;
    flex-direction: column;
    gap: 1.75rem;
}

.education-item {
    display: flex;
    align-items: flex-start;
    gap: 1rem;
}

.education-marker {
    display: flex;
    flex-shrink: 0;
    align-items: center;
    justify-content: center;
    width: 38px;
    height: 38px;
    background: #f3e5dc;
    border-radius: 8px;
    color: #984d3b;
    font-size: 0.75rem;
    font-weight: 700;
}

.education-content {
    min-width: 0;
}

.period {
    margin: 0 0 0.35rem;
    color: #b85f4b;
    font-size: 0.8rem;
    font-weight: 700;
}

.education-content h3 {
    margin: 0 0 0.35rem;
    font-size: 1.2rem;
    line-height: 1.4;
}

.institution {
    margin: 0;
    color: #68665d;
    font-size: 0.95rem;
    line-height: 1.7;
}

.document-link {
    display: inline-flex;
    align-items: center;
    gap: 0.5rem;
    margin-top: 0.8rem;
    color: #ad523e;
    font-size: 0.9rem;
    font-weight: 600;
    text-decoration: none;
    transition: color 0.2s ease;
}

.document-link:hover {
    color: #823c2d;
    text-decoration: underline;
    text-underline-offset: 4px;
}

.interests-list {
    display: flex;
    flex-wrap: wrap;
    gap: 0.7rem;
}

.interest-tag {
    padding: 0.65rem 1rem;
    background: #f6eee5;
    border: 1px solid #ead9ca;
    border-radius: 6px;
    color: #755247;
    font-size: 0.9rem;
    transition: background 0.2s ease, border-color 0.2s ease;
}

.interest-tag:hover {
    background: #f3e5dc;
    border-color: #dba08e;
}

@media (max-width: 760px) {
    .about {
        padding: 3rem 1.25rem;
    }

    .page-heading {
        margin-bottom: 2rem;
    }

    .profile {
        grid-template-columns: 1fr;
        gap: 2rem;
        margin-bottom: 3rem;
    }

    .about-photo {
        width: min(250px, 80%);
        margin: 0 auto;
    }

    .about-photo img {
        height: 300px;
    }

    .hero-text h2 {
        font-size: 2rem;
    }

    .section {
        padding: 1.4rem;
    }

    .section-heading h2 {
        font-size: 1.5rem;
    }

    .education-item {
        gap: 0.75rem;
    }

    .education-content h3 {
        font-size: 1.1rem;
    }
}

@media (prefers-reduced-motion: reduce) {

    .document-link,
    .interest-tag {
        transition: none;
    }
}
</style>
