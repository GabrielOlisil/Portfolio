<script setup lang="ts">
interface StackItem {
  name: string;
  icon: string;
  color: string;
}

const stack: StackItem[] = [
  { name: 'C#', icon: '⚙️', color: 'badge-primary' },
  { name: '.NET', icon: '🟣', color: 'badge-secondary' },
  { name: 'Docker', icon: '🐳', color: 'badge-info' },
  { name: 'Vue.js', icon: '💚', color: 'badge-success' },
  { name: 'TypeScript', icon: '🔷', color: 'badge-accent' },
];
</script>

<template>
  <section id="stack" class="py-20 px-6 bg-base-200">
    <div class="max-w-4xl mx-auto text-center">
      <h2 class="text-3xl font-bold mb-2">Tech Stack</h2>
      <p class="text-base-content/60 mb-10">Tecnologias que utilizo no dia a dia</p>

      <div class="flex flex-wrap justify-center gap-4">
        <div
          v-for="tech in stack"
          :key="tech.name"
          class="badge gap-2 p-5 text-lg font-medium cursor-default"
          :class="tech.color"
        >
          <span class="text-xl">{{ tech.icon }}</span>
          {{ tech.name }}
        </div>
      </div>
    </div>
  </section>
</template>
