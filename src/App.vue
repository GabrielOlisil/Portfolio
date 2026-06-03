<script setup lang="ts">
import NavBar from './components/NavBar.vue'
import HeroSection from './components/HeroSection.vue'
import StackSection from './components/StackSection.vue'
import ProjectsSection from './components/ProjectsSection.vue'
import FooterSection from './components/FooterSection.vue'
</script>

<template>
  <NavBar />
  <main>
    <HeroSection />
    <StackSection />
    <ProjectsSection />
  </main>
  <FooterSection />
</template>
