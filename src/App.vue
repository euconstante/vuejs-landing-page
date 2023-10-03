<script>
import TheNavbar from './components/TheNavbar.vue'
import TheFooter from './components/TheFooter.vue'
import './assets/styles/style.css'
import './assets/styles/sizes.css'
import './assets/styles/spacing.css'
import './assets/styles/colors.css'
import './assets/styles/text.css'

export default {
  components: {
    TheNavbar,
    TheFooter,
  },
}
</script>

<template>
  <TheNavbar />
  <RouterView />
  <TheFooter />
</template>

<style></style>
