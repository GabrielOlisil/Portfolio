<script setup lang="ts">
import {
  SvglCSharpLogo,
  SvglMicrosoftNETLogo,
  SvglDockerLogo,
  SvglVueLogo,
  SvglTypeScriptLogo,
} from '@selemondev/svgl-vue';
import { type Component } from 'vue';

interface StackItem {
  name: string;
  icon: Component;
}

const stack: StackItem[] = [
  { name: 'C#', icon: SvglCSharpLogo },
  { name: '.NET', icon: SvglMicrosoftNETLogo },
  { name: 'Docker', icon: SvglDockerLogo },
  { name: 'Vue.js', icon: SvglVueLogo },
  { name: 'TypeScript', icon: SvglTypeScriptLogo },
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
          class="badge badge-outline gap-3 px-5 py-4 text-base font-medium cursor-default"
        >
          <div class="w-5 h-5 shrink-0 flex items-center justify-center [&>svg]:w-full [&>svg]:h-full">
            <component :is="tech.icon" />
          </div>
          {{ tech.name }}
        </div>
      </div>
    </div>
  </section>
</template>
