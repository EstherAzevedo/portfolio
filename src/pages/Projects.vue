<script setup lang="ts">
import Navbar from '@/components/Navbar.vue';
import stareviewLogo from '/public/stareview_bg_light.png';
import phpLogo from '/public/php_elefante.png';
import { ref } from 'vue'

interface Project {
    id: number
    title: string
    description: string
    technologies: string[]
    githubUrl?: string
    liveUrl?: string
    image?: string
}

const projects = ref<Project[]>([
    {
        id: 1,
        title: 'Em desenvolvimento',
        description: 'Aplicação web para resenhas literárias com integração social e gamificação. Permite aos usuários compartilhar opiniões sobre livros, interagir com outros leitores e descobrir novas leituras.',
        technologies: ['Vue.js', 'TypeScript', 'Vite', 'Tailwind CSS'],
        githubUrl: 'https://github.com/EstherAzevedo/stareview-frontend',
        image: stareviewLogo
    },
    {
        id: 2,
        title: 'PHP Auth System',
        description: 'O projeto implementa funcionalidades essenciais de autenticação, incluindo cadastro, login, logout, gerenciamento de sessões, páginas protegidas e armazenamento seguro de senhas utilizando password_hash() e password_verify().',
        technologies: ['PHP', 'MySQL', 'HTML', 'CSS', 'JavaScript', 'Apache'],
        githubUrl: 'https://github.com/EstherAzevedo/php-auth-system.git',
        image: phpLogo
    },
    {
        id: 3,
        title: 'Project Example 3',
        description: 'A third example showing how the cards look with different content.',
        technologies: ['Python', 'Django', 'PostgreSQL'],
        githubUrl: 'https://github.com'
    }
])
</script>

<template>
    <Navbar />

    <main class="projects">
        <header class="header">
            <h1>Projects<span>.</span></h1>
            <p class="subtitle">
                A collection of projects I've built while exploring and developing my skills.
            </p>
        </header>

        <section class="projects-grid">
            <article v-for="(project, index) in projects" :key="project.id" class="project-card">
                <div class="project-top">
                    <span class="project-number">
                        {{ String(index + 1).padStart(2, '0') }}
                    </span>

                    <span v-if="index === 0" class="project-status">
                        In progress
                    </span>
                </div>

                <div v-if="project.image" class="project-visual">
                    <img :src="project.image" :alt="`${project.title} logo`" class="project-image" />
                </div>

                <div class="card-content">
                    <h2>{{ project.title }}</h2>

                    <p class="description">
                        {{ project.description }}
                    </p>

                    <div class="technologies">
                        <span v-for="tech in project.technologies" :key="tech" class="tech-tag">
                            {{ tech }}
                        </span>
                    </div>

                    <div class="card-footer">
                        <a v-if="project.githubUrl" :href="project.githubUrl" target="_blank" rel="noopener noreferrer"
                            class="project-link">
                            <svg xmlns="http://www.w3.org/2000/svg" width="18" height="18" fill="currentColor"
                                viewBox="0 0 24 24" aria-hidden="true">
                                <path
                                    d="M12 .3a12 12 0 0 0-3.8 23.4c.6.1.8-.2.8-.6v-2.2c-3.3.7-4-1.6-4-1.6a3.2 3.2 0 0 0-1.3-1.7c-1-.7.1-.7.1-.7a2.6 2.6 0 0 1 1.9 1.3 2.7 2.7 0 0 0 3.6 1 2.7 2.7 0 0 1 .8-1.7c-2.6-.3-5.4-1.3-5.4-6a4.7 4.7 0 0 1 1.2-3.2 4.4 4.4 0 0 1 .1-3.1s1-.3 3.3 1.2a11.4 11.4 0 0 1 6 0c2.3-1.5 3.3-1.2 3.3-1.2a4.4 4.4 0 0 1 .1 3.1 4.7 4.7 0 0 1 1.2 3.2c0 4.7-2.8 5.6-5.4 5.9a2.9 2.9 0 0 1 .8 2.2v3.2c0 .4.2.7.8.6A12 12 0 0 0 12 .3" />
                            </svg>

                            View on GitHub
                            <span class="link-arrow">↗</span>
                        </a>
                    </div>
                </div>
            </article>
        </section>
    </main>
</template>

<style scoped>
.projects {
    min-height: 100vh;
    padding: 5rem 2rem 4rem;
    background: #f4f1de;
    color: #292820;
    box-sizing: border-box;
}

.header {
    max-width: 1100px;
    margin: 0 auto 3rem;
}

.eyebrow {
    margin: 0 0 0.9rem;
    color: #b85f4b;
    font-size: 0.75rem;
    font-weight: 700;
    letter-spacing: 2.5px;
}

.header h1 {
    margin: 0;
    font-size: clamp(2.5rem, 5vw, 3.8rem);
    line-height: 1.1;
    letter-spacing: -1.8px;
    color: #292820;
}

.header h1 span {
    color: #c96851;
}

.subtitle {
    max-width: 540px;
    margin-top: 1rem;
    color: #68665d;
    font-size: 1.05rem;
    line-height: 1.8;
}

.projects-grid {
    display: grid;
    grid-template-columns: repeat(2, minmax(0, 1fr));
    gap: 1.5rem;
    max-width: 1100px;
    margin: 0 auto;
    align-items: stretch;
}

.project-card {
    position: relative;
    display: flex;
    flex-direction: column;
    min-width: 0;
    padding: 1.25rem;
    background: #fffdf6;
    border: 1px solid #e5deca;
    border-radius: 14px;
    overflow: hidden;
    transition:
        transform 0.25s ease,
        box-shadow 0.25s ease,
        border-color 0.25s ease;
}

.project-card::before {
    content: '';
    position: absolute;
    top: 0;
    left: 1.25rem;
    right: 1.25rem;
    height: 3px;
    background: #dba08e;
    transform: scaleX(0);
    transform-origin: left;
    transition: transform 0.25s ease;
}

.project-card:hover {
    transform: translateY(-4px);
    border-color: #dba08e;
    box-shadow: 0 12px 28px rgba(65, 48, 35, 0.08);
}

.project-card:hover::before {
    transform: scaleX(1);
}

.project-top {
    display: flex;
    align-items: center;
    justify-content: space-between;
    gap: 1rem;
    min-height: 24px;
    margin-bottom: 1rem;
}

.project-number {
    color: #b85f4b;
    font-size: 0.8rem;
    font-weight: 700;
    letter-spacing: 1px;
}

.project-status {
    padding: 0.35rem 0.65rem;
    color: #984d3b;
    background: #f3e5dc;
    border-radius: 20px;
    font-size: 0.72rem;
    font-weight: 600;
}

.project-visual {
    display: flex;
    align-items: center;
    justify-content: center;
    height: 180px;
    margin-bottom: 1.5rem;
    padding: 1.5rem;
    background: #f4f0e5;
    border: 1px solid #eee7d7;
    border-radius: 9px;
    box-sizing: border-box;
}

.project-image {
    display: block;
    max-width: 85%;
    max-height: 125px;
    object-fit: contain;
}

.card-content {
    display: flex;
    flex: 1;
    flex-direction: column;
}

.project-card h2 {
    margin: 0 0 0.8rem;
    color: #292820;
    font-size: 1.35rem;
    line-height: 1.4;
}

.description {
    margin: 0 0 1.4rem;
    color: #68665d;
    font-size: 0.94rem;
    line-height: 1.8;
}

.technologies {
    display: flex;
    flex-wrap: wrap;
    gap: 0.45rem;
    margin-top: auto;
    margin-bottom: 1.5rem;
}

.tech-tag {
    padding: 0.4rem 0.7rem;
    color: #755247;
    background: #f6eee5;
    border: 1px solid #ead9ca;
    border-radius: 5px;
    font-size: 0.78rem;
}

.card-footer {
    padding-top: 1rem;
    border-top: 1px solid #eee7d7;
}

.project-link {
    display: inline-flex;
    align-items: center;
    gap: 0.55rem;
    color: #ad523e;
    font-size: 0.9rem;
    font-weight: 600;
    text-decoration: none;
    transition: color 0.2s ease;
}

.project-link:hover {
    color: #823c2d;
}

.project-link svg {
    flex-shrink: 0;
}

.link-arrow {
    transition: transform 0.2s ease;
}

.project-link:hover .link-arrow {
    transform: translate(2px, -2px);
}

@media (max-width: 760px) {
    .projects {
        padding: 3.5rem 1.25rem;
    }

    .header {
        margin-bottom: 2rem;
    }

    .projects-grid {
        grid-template-columns: 1fr;
        gap: 1.25rem;
    }

    .project-card {
        padding: 1rem;
    }

    .project-visual {
        height: 160px;
    }
}

@media (prefers-reduced-motion: reduce) {

    .project-card,
    .project-card::before,
    .project-link,
    .link-arrow {
        transition: none;
    }

    .project-card:hover,
    .project-link:hover .link-arrow {
        transform: none;
    }
}
</style>
