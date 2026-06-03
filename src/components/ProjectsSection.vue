<script setup lang="ts">
import { ExternalLink, Lightbulb } from '@lucide/vue';
import GithubIcon from './GithubIcon.vue';

interface Project {
  title: string;
  description: string;
  githubUrl: string;
  tags: string[];
  learnings: string[];
}

const projects: Project[] = [
  {
    title: 'E-commerce Modular',
    description: 'Sistema de e-commerce com arquitetura modular em Django, incluindo carrinho, catálogo, pedidos, pagamentos e gestão de usuários.',
    githubUrl: 'https://github.com/GabrielOlisil',
    tags: ['Python', 'Django', 'PostgreSQL'],
    learnings: [
      'Arquitetura modular com Django Apps',
      'Integração de sistemas de pagamento',
      'Modelagem de dados relacional',
    ],
  },
  {
    title: 'App de Gestão de Patrimônio',
    description: 'Aplicativo Flutter para rastreamento de patrimônio institucional com Firebase Firestore, usando MVVM + Provider.',
    githubUrl: 'https://github.com/GabrielOlisil',
    tags: ['Flutter', 'Firebase', 'Dart'],
    learnings: [
      'Padrão MVVM com Provider',
      'CRUD completo com Firestore',
      'Paginação e filtros inteligentes',
    ],
  },
  // Adicione mais projetos aqui seguindo o mesmo formato
];
</script>

<template>
  <section id="projetos" class="py-20 px-6 bg-base-100">
    <div class="max-w-5xl mx-auto">
      <div class="text-center mb-12">
        <h2 class="text-3xl font-bold mb-2">Projetos</h2>
        <p class="text-base-content/60">O que construí e o que aprendi</p>
      </div>

      <div class="grid grid-cols-1 md:grid-cols-2 gap-8">
        <div
          v-for="project in projects"
          :key="project.title"
          class="card bg-base-200 shadow-xl border border-base-300"
        >
          <div class="card-body">
            <h3 class="card-title text-primary">
              {{ project.title }}
            </h3>
            <p class="text-base-content/70 text-sm">
              {{ project.description }}
            </p>

            <!-- Tags -->
            <div class="flex flex-wrap gap-2 mt-2">
              <span
                v-for="tag in project.tags"
                :key="tag"
                class="badge badge-outline badge-sm"
              >
                {{ tag }}
              </span>
            </div>

            <!-- Learnings -->
            <div class="mt-4">
              <div class="flex items-center gap-2 text-sm font-semibold text-secondary mb-2">
                <Lightbulb :size="16" />
                O que aprendi
              </div>
              <ul class="text-sm text-base-content/70 space-y-1">
                <li v-for="learning in project.learnings" :key="learning" class="flex items-start gap-2">
                  <span class="text-primary mt-0.5">▸</span>
                  {{ learning }}
                </li>
              </ul>
            </div>

            <!-- Actions -->
            <div class="card-actions justify-end mt-4">
              <a
                :href="project.githubUrl"
                target="_blank"
                rel="noopener"
                class="btn btn-sm btn-primary gap-2"
              >
                <GithubIcon :size="14" />
                Código
              </a>
            </div>
          </div>
        </div>
      </div>

      <!-- Hint to add more -->
      <div class="text-center mt-10">
        <a
          href="https://github.com/GabrielOlisil?tab=repositories"
          target="_blank"
          rel="noopener"
          class="btn btn-outline btn-sm gap-2"
        >
          <ExternalLink :size="14" />
          Ver todos no GitHub
        </a>
      </div>
    </div>
  </section>
</template>
