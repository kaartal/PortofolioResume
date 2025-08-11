<template>
  <NavBar />
  <HeroSection />
  <SkillsSection />
</template>

<script setup>
// IMPORT COMPONENT ASYNCHRONE METHOD
import { defineAsyncComponent } from 'vue'
const NavBar = defineAsyncComponent(() => import('@/components/Navbar.vue'));
const HeroSection = defineAsyncComponent(() => import('@/components/Herosection.vue'));
const SkillsSection = defineAsyncComponent(() => import('@/components/SkillsSection.vue'));
</script>
