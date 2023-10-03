<script lang="ts">
import { defineComponent } from 'vue'
import CardCarousel from './CardCarousel.vue'
import CardMovie from './CardMovie.vue'

import hickingImg from '@/assets/images/hicking.png'
import drawingImg from '@/assets/images/drawing.png'
import dancingImg from '@/assets/images/dancing.png'
import fleabagImg from '@/assets/images/fleabag.jpeg'
import shutterImg from '@/assets/images/shutter-island.jpg'
import officeImg from '@/assets/images/the-office.jpg'
import trueImg from '@/assets/images/true-detective.jpeg'
import onepieceImg from '@/assets/images/onepiece.jpeg'

import '../assets/styles/components/AboutSection.css'

export default defineComponent({
  components: {
    CardCarousel,
    CardMovie,
  },
  data() {
    return {
      carouselImages: [hickingImg, dancingImg, drawingImg],
      carouselText: [
        "It's essential to find a work-life balance and connect with nature. To do that, I love camping, hiking, and exploring!",
        'Love being in touch with culture, and last year, I started to get involved in the world of dance!',
        "Always been drawing since I was a kid. I love doing it by hand, especially realistic artwork. It's probably why I'm a detail-oriented person.",
      ],
      carouselTitle: ['Hicking', 'Dancing', 'Drawing'],
      cardItems: [
        {
          image: fleabagImg,
        },
        {
          image: shutterImg,
        },
        {
          image: onepieceImg,
        },
        {
          image: officeImg,
        },
        {
          image: trueImg,
        },
      ],
    }
  },
})
</script>

<template>
  <section id="about" class="about-section spacing--sides">
    <div class="about-content">
      <h2 class="title">About me</h2>
      <p class="spacing--small">
        This section is more about getting to know me than showcasing professional assets, which you can find in
        <a
          class="link"
          href="https://docs.google.com/document/d/1Jqz7rSRfOVn7gvL1Qtqn5uQSfF29poo3/edit?usp=sharing&ouid=100392245811128930038&rtpof=true&sd=true"
          target="_blank"
          >my resume</a
        >.
      </p>
      <div class="about-profile container--mobile">
        <p class="about-section__text container--small">
          As you probably already know, I'm Bianca Guedert, a Brazilian woman, and a Master's degree holder in
          engineering. I didn't come from a privileged background; in fact, I'm the first in my family to earn a degree
          and the only one who speaks a second language. This is why learning is the most valuable tool for me. These
          are aspects you wouldn't typically find in a resume, but they have strongly shaped my values and mindset,
          contributing to my achievements.
        </p>
        <figure class="spacing--sides">
          <img class="about-section__avatar spacing" src="../assets/images/profile.png" width="250px" />
        </figure>
        <p class="about-section__text container--small">
          I'm currently based in Brazil-SC and have lived with 30+ people, fostering sociability. Early independence and
          diverse work experiences in sales, engineering, and finally transitioning to tech, the field I've always
          wanted to be in. Now, I'm ready for the next chapter in my life and eager to embark on an international
          career. This motivation extends beyond the professional realm; personally, I'm excited to embrace new
          experiences and engage in cultural exchanges.
        </p>
      </div>
      <hr />
      <p class="title--small">My Interests</p>
    </div>
    <div class="about-slider">
      <CardCarousel :images="carouselImages" :text="carouselText" :title="carouselTitle" :slideInterval="3000" />
    </div>
    <div class="about-movies">
      <hr />
      <div>
        <h2 class="title--small">Favorite TV shows</h2>
        <p class="description spacing--small">
          Of course, this couldn't be left behind! As the main question at JustWatch, these are some of my favorite TV
          shows
        </p>
      </div>
      <div class="about-cards">
        <CardMovie
          v-for="(item, index) in cardItems"
          :key="index"
          :image="item.image"
          :title="item.title"
          :description="item.description"
        />
      </div>
    </div>
  </section>
</template>

<style></style>
