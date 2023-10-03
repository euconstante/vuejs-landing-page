<script>
import Slide from '@/components/Slide.vue'

import '../assets/styles/components/DiscoverSection.css'

export default {
  components: {
    Slide,
  },
}
</script>

<template>
  <section id="discover" class="hero__discover spacing--sides">
    <h2 class="subtitle">How I am a great fit ?</h2>
    <p class="spacing--small">What I can offer after 3 years of experience as a frontend developer</p>
    <p class="title--small">Top 10 <br />reasons</p>

    <Slide />
    <h3 class="title--small discover__title">Why JustWatch ?</h3>
    <div class="discover__text">
      <p class="description--medium">
        I'm genuinely excited about the prospect of working at JustWatch. The company's unique position as a media
        company tailored for today's entertainment landscape is truly remarkable. The comprehensive understanding of
        audiences and content derived from billions of data points across the largest streaming guide in the world is
        impressive. JustWatch's mission to connect entertainment enthusiasts with their favorite content globally
        resonates with my passion for technology and entertainment. Moreover, the company's emphasis on individual
        growth and personal development aligns perfectly with my professional aspirations. JustWatch's commitment to
        learning, delivering results, and creating value strongly appeals to me, and I believe that contributing to such
        a dynamic and forward-thinking organization would be an incredible opportunity. I'm eager to be part of a
        company that not only shares these values but also actively practices them in its day-to-day operations, and I
        believe my skills and mindset would be a valuable addition to the JustWatch team.
      </p>
    </div>
  </section>
</template>

<style scoped></style>
