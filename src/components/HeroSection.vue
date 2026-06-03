<script setup lang="ts">
import { ChevronDown } from '@lucide/vue';
import GithubIcon from './GithubIcon.vue';
</script>

<template>
  <section id="sobre" class="hero min-h-[85vh] bg-base-100">
    <div class="hero-content flex-col lg:flex-row-reverse gap-12 max-w-6xl mx-auto px-6">
      <!-- Avatar -->
      <div class="animate-fade-in-up">
        <div class="avatar placeholder">
          <div class="bg-primary text-primary-content w-48 h-48 rounded-full ring ring-primary ring-offset-base-100 ring-offset-4 shadow-2xl">
            <img src="/profile.jpeg" alt="Gabriel Oliveira" class="w-full h-full object-cover" />
          </div>
        </div>
      </div>

      <!-- Text content -->
      <div class="max-w-xl">
        <p class="text-primary font-medium mb-2 animate-fade-in-up" style="opacity: 0;">
          Olá, eu sou
        </p>
        <h1 class="text-5xl lg:text-6xl font-extrabold animate-fade-in-up animation-delay-100" style="opacity: 0;">
          Gabriel Oliveira
        </h1>
        <p class="text-xl text-base-content/70 mt-4 animate-fade-in-up animation-delay-200" style="opacity: 0;">
          Desenvolvedor Full Stack
        </p>
        <div class="divider divider-primary w-24 animate-fade-in-up animation-delay-200" style="opacity: 0;"></div>
        <p class="text-base-content/80 leading-relaxed animate-fade-in-up animation-delay-300" style="opacity: 0;">
          Técnico em Informática pelo <span class="font-semibold text-primary">IFRO</span> e
          formando em <span class="font-semibold text-primary">Análise e Desenvolvimento de Sistemas</span>
          pelo IFRO. Apaixonado por criar soluções eficientes com tecnologias modernas.
        </p>

        <!-- Action buttons -->
        <div class="flex flex-wrap gap-3 mt-6 animate-fade-in-up animation-delay-400" style="opacity: 0;">
          <a href="#projetos" class="btn btn-primary btn-md gap-2">
            Ver Projetos
            <ChevronDown :size="18" />
          </a>
          <a href="https://github.com/GabrielOlisil" target="_blank" rel="noopener" class="btn btn-outline btn-md gap-2">
            <GithubIcon :size="18" />
            GitHub
          </a>
        </div>
      </div>
    </div>
  </section>
</template>
