<script setup lang="ts">
import { ExternalLink, Lightbulb } from '@lucide/vue';
import GithubIcon from './GithubIcon.vue';

interface Project {
  title: string;
  description: string;
  githubUrl: string;
  tags: string[];
  learnings: string[];
  highlight?: boolean;
}

const projects: Project[] = [
  {
    title: 'DungeonWorldFichaV2',
    description: 'Sistema de fichas para Dungeon World com arquitetura de microserviços. Backend em .NET, serviço de dados em TypeScript, e frontend Vue — todos orquestrados com Docker Compose. Utiliza RabbitMQ para comunicação assíncrona entre serviços e WebSockets para atualização em tempo real das fichas dos jogadores.',
    githubUrl: 'https://github.com/GabrielOlisil/DungeonWorldFichaV2',
    tags: ['C#', '.NET', 'TypeScript', 'Vue', 'RabbitMQ', 'WebSocket', 'Docker'],
    learnings: [
      'Integração de microserviços com RabbitMQ (message broker)',
      'Comunicação em tempo real com WebSockets',
      'Orquestração de múltiplos serviços com Docker Compose',
      'Arquitetura distribuída — "bazuca pra matar formiga", mas o aprendizado valeu',
    ],
    highlight: true,
  },
  {
    title: 'AriCrimes',
    description: 'Solução completa para gerenciamento de ocorrências urbanas, composta por 4 repositórios: API (Python), app mobile (Flutter), file server (Node.js) e painel admin (Vue). Integra Google APIs e geolocalização para gerar mapas de calor de crimes na cidade.',
    githubUrl: 'https://github.com/GabrielOlisil/AriCrimesMobile',
    tags: ['Flutter', 'Python', 'Vue', 'Node.js', 'Google Maps API', 'Geolocation', 'Docker'],
    learnings: [
      'Integração com Google Maps API e geolocalização',
      'Geração de mapas de calor (heatmaps) a partir de dados geolocalizados',
      'Arquitetura multi-repo: API, Mobile, File Server e Admin',
      'Comunicação entre serviços distintos (mobile ↔ API ↔ file server)',
    ],
  },
  {
    title: 'InsertGeneration',
    description: 'Ferramenta em C# que gera comandos SQL INSERT automaticamente a partir de entidades. Projeto focado em explorar princípios SOLID, com uso de inversão de controle via interfaces para permitir suporte a múltiplos bancos de dados com um único código principal.',
    githubUrl: 'https://github.com/GabrielOlisil/InsertGeneration',
    tags: ['C#', '.NET', 'SOLID'],
    learnings: [
      'Inversão de Controle (IoC) com interfaces',
      'Suporte a múltiplos bancos de dados com um único código',
      'Princípios SOLID aplicados na prática',
      'Geração dinâmica de SQL via reflexão',
    ],
  },
  {
    title: 'Gestão de Patrimônio',
    description: 'Aplicativo Flutter para rastreamento de patrimônio institucional ("tombamentos") utilizando Firebase como BaaS (Backend as a Service). Arquitetura MVVM com Provider para gerenciamento de estado.',
    githubUrl: 'https://github.com/GabrielOlisil/tombamentos',
    tags: ['Flutter', 'Firebase', 'Dart'],
    learnings: [
      'Firebase como Backend as a Service (BaaS)',
      'Padrão MVVM com Provider para gerenciamento de estado',
      'CRUD completo com Firestore',
      'Paginação e filtros inteligentes',
    ],
  },
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
          :class="{ 'md:col-span-2 border-primary/30': project.highlight }"
        >
          <div class="card-body">
            <div class="flex items-center gap-2">
              <h3 class="card-title text-primary">
                {{ project.title }}
              </h3>
              <span v-if="project.highlight" class="badge badge-primary badge-sm">destaque</span>
            </div>
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
