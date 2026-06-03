<script setup lang="ts">
import { Heart } from '@lucide/vue';
import GithubIcon from './GithubIcon.vue';

const currentYear = new Date().getFullYear();
</script>

<template>
  <footer id="contato" class="footer footer-center bg-base-200 text-base-content p-10 border-t border-base-300">
    <nav>
      <div class="grid grid-flow-col gap-4">
        <a href="https://github.com/GabrielOlisil" target="_blank" rel="noopener" class="btn btn-ghost btn-circle hover:text-primary transition-colors" aria-label="GitHub">
          <GithubIcon :size="24" />
        </a>
      </div>
    </nav>
    <aside>
      <p class="flex items-center gap-1 text-base-content/60">
        Feito com <Heart :size="14" class="text-error" /> por Gabriel — {{ currentYear }}
      </p>
    </aside>
  </footer>
</template>
