<script>
import CustomButton from './CustomButton.vue'

import '../assets/styles/components/ContactSection.css'

export default {
  components: { CustomButton },
}
</script>

<template>
  <section class="container--centered spacing--large" id="contact">
    <div class="section__content">
      <img src="images/logo.svg" width="80" alt="Section Image" class="section__image" />

      <p class="title--small spacing--sides">
        Have I caught your attention up to this point? <br /><br />JustWatch my contacts:
      </p>
      <a class="contact__link spacing--top" href="https://www.linkedin.com/in/biancaguedert/" target="_blank"
        >LinkedIn</a
      >
      <a class="contact__link spacing--top" href="https://github.com/euconstante" target="_blank">GitHub</a>
      <a class="contact__link spacing--top" href="mailto:constanteguedert@gmail.com" target="_blank">Gmail</a>
      <p class="spacing--small">+55 48 9 88560619</p>
      <CustomButton
        primary
        buttonName="Lets talk !"
        href="https://calendar.google.com/calendar/u/0?cid=Y29uc3RhbnRlZ3VlZGVydEBnbWFpbC5jb20"
        target="_blank"
      />
    </div>
  </section>
</template>

<style></style>
