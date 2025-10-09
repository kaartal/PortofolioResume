<template>
  <!-- <Preloader v-if="loading" />
  <template v-else>-->
    <ColorTrail />
    <NavBar />
    <HeroSection id="about" />
    <SkillsSection id="skills" />
    <ProjectSection id="projects" />
    <LearningSteps id="timeline" />
    <Time />
    <Footer />

</template>

<script setup>
import { ref, onMounted } from "vue";
import { defineAsyncComponent } from "vue";

const loading = ref(true);

const NavBar = defineAsyncComponent(() => import("@/components/NavBar.vue"));
const HeroSection = defineAsyncComponent(() =>
  import("@/components/HeroSection.vue")
);
const SkillsSection = defineAsyncComponent(() =>
  import("@/components/SkillsSection.vue")
);
const ColorTrail = defineAsyncComponent(() =>
  import("@/components/ColorTrail.vue")
);
const ProjectSection = defineAsyncComponent(() =>
  import("@/components/ProjectSection.vue")
);
const LearningSteps = defineAsyncComponent(() =>
  import("@/components/LearningSteps.vue")
);
const Footer = defineAsyncComponent(() => import("@/components/Footer.vue"));
const Time = defineAsyncComponent(() => import("@/components/Time.vue"));
import Preloader from "@/components/Preloader.vue";

onMounted(() => {
  setTimeout(() => {
    loading.value = false;
  }, 7000);
});
</script>
