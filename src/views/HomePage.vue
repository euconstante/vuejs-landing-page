<script>
import HeroSection from '@/components/HeroSection.vue'
import DiscoverSection from '@/components/DiscoverSection.vue'
import ContactSection from '@/components/ContactSection.vue'
import AboutSection from '@/components/AboutSection.vue'

export default {
  components: {
    HeroSection,
    DiscoverSection,
    ContactSection,
    AboutSection,
  },
}
</script>

<template>
  <main>
    <HeroSection />
    <span class="nav--secondary"></span>
    <DiscoverSection />
    <AboutSection />
    <ContactSection />
  </main>
</template>

<style scoped>
.nav--secondary {
  background: black;
  width: 100%;
  display: flex;
  position: sticky;
  top: 0;
  height: 5rem;
  z-index: 1;
}
</style>
