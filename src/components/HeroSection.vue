<script>
import CustomButton from '@/components/CustomButton.vue'
import jsIcon from '@/assets/icons/js.svg'
import htmlIcon from '@/assets/icons/html5.svg'
import cssIcon from '@/assets/icons/css.svg'
import vueIcon from '@/assets/icons/vuejs.png'
import tsIcon from '@/assets/icons/typescript.png'
import reactIcon from '@/assets/icons/reactjs.svg'
import saasIcon from '@/assets/icons/sass.svg'
import gitIcon from '@/assets/icons/gitlab.svg'

import '../assets/styles/components/HeroSection.css'

export default {
  props: {
    href: String,
    target: String,
  },
  components: {
    CustomButton,
  },
  data() {
    return {
      techIcons: [tsIcon, jsIcon, htmlIcon, cssIcon, reactIcon, vueIcon, saasIcon, gitIcon],
    }
  },
}
</script>
<template>
  <section class="hero">
    <div class="hero__content">
      <h1 class="hero__title title">Bianca Guedert</h1>
      <h2 class="hero__subtitle subtitle spacing--medium">
        Your guide to learning <br />more about me and why <br />I'm a great fit for the Frontend position.
      </h2>
      <div class="container--centered spacing--small">
        <CustomButton primary href="#discover" buttonName="Discover" />
        <CustomButton
          secondary
          href="https://docs.google.com/document/d/1Jqz7rSRfOVn7gvL1Qtqn5uQSfF29poo3/edit?usp=sharing&ouid=100392245811128930038&rtpof=true&sd=true"
          buttonName="Resume"
          target="_blank"
        />
      </div>
      <p class="subtitle--small">Technical skills</p>
      <div class="container--centered spacing--small">
        <figure v-for="(icon, index) in techIcons" :key="index" class="container--centered">
          <img :src="icon" alt="Tech Icon" class="icon--large icon--small" />
        </figure>
      </div>
      <p>
        In a hurry?
        <a
          class="link"
          href="https://docs.google.com/document/d/1crVkNfTD2OaXQHzGLOvloqYfTpGpBc5RGfYcf3D-uWw/edit?usp=sharing"
          target="_blank"
        >
          Access the short cover letter</a
        >
      </p>
    </div>

    <figure>
      <img class="hero__image" src="/images/global-home-bg-comp.png" />
    </figure>

    <div class="hero__gradient gradient"></div>
  </section>
</template>

<style></style>
