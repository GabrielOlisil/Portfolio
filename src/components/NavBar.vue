<script setup lang="ts">
import { User, FolderGit2, Code2, Mail } from '@lucide/vue';

const navItems = [
  { label: 'Sobre', href: '#sobre', icon: User },
  { label: 'Stack', href: '#stack', icon: Code2 },
  { label: 'Projetos', href: '#projetos', icon: FolderGit2 },
  { label: 'Contato', href: '#contato', icon: Mail },
];
</script>

<template>
  <div class="navbar bg-base-200/80 backdrop-blur-md sticky top-0 z-50 shadow-lg border-b border-base-300">
    <div class="navbar-start">
      <div class="dropdown">
        <div tabindex="0" role="button" class="btn btn-ghost lg:hidden">
          <svg xmlns="http://www.w3.org/2000/svg" class="h-5 w-5" fill="none" viewBox="0 0 24 24" stroke="currentColor">
            <path stroke-linecap="round" stroke-linejoin="round" stroke-width="2" d="M4 6h16M4 12h8m-8 6h16" />
          </svg>
        </div>
        <ul tabindex="0" class="menu menu-sm dropdown-content bg-base-200 rounded-box z-10 mt-3 w-52 p-2 shadow-lg">
          <li v-for="item in navItems" :key="item.label">
            <a :href="item.href" class="gap-2">
              <component :is="item.icon" :size="16" />
              {{ item.label }}
            </a>
          </li>
        </ul>
      </div>
      <a href="#" class="btn btn-ghost text-xl font-bold">
        <span class="text-primary">&lt;</span>Gabriel<span class="text-primary">/&gt;</span>
      </a>
    </div>
    <div class="navbar-end hidden lg:flex">
      <ul class="menu menu-horizontal px-1 gap-1">
        <li v-for="item in navItems" :key="item.label">
          <a :href="item.href" class="gap-2 hover:text-primary transition-colors">
            <component :is="item.icon" :size="16" />
            {{ item.label }}
          </a>
        </li>
      </ul>
    </div>
  </div>
</template>
