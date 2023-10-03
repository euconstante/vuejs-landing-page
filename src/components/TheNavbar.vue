<script>
export default {
  props: ['tagline'],
  data: () => ({
    navList: [
      {
        name: 'Home',
        path: '/',
      },
      { name: 'Discover', path: '#discover' },
      {
        name: 'About',
        path: '#about',
      },
      {
        name: 'Contact',
        path: '#contact',
      },
    ],
  }),
  computed: {
    brazilFormattedDateTime() {
      const options = {
        timeZone: 'America/Sao_Paulo',
        hour: 'numeric',
        minute: 'numeric',
      }
      const locale = 'en-US'
      return new Date().toLocaleString(locale, options)
    },
    berlinFormattedDateTime() {
      const options = {
        timeZone: 'Europe/Berlin',
        hour: 'numeric',
        minute: 'numeric',
      }
      const locale = 'en-US'
      return new Date().toLocaleString(locale, options)
    },
  },
}
</script>

<template>
  <nav class="navbar container--between spacing-small">
    <div class="navbar__brand">
      <RouterLink to="/" class="navbar__item">
        <img src="@/assets/icons/JustWatch-logo-large.png" alt="" class="icon--large icon-small" />
      </RouterLink>
    </div>
    <div class="navbar__menu">
      <p class="hide">Brazil UTC-3: {{ brazilFormattedDateTime }}</p>
      -
      <p class="hide">Berlin UTC+1: {{ berlinFormattedDateTime }}</p>
      <div v-for="navItem in navList" :key="`nav-${navItem.name}`">
        <a class="navbar__link" :href="navItem.path">{{ navItem.name }}</a>
      </div>
    </div>
  </nav>
</template>

<style>
.navbar {
  color: var(--text-color);
  width: 90%;
  position: fixed;
  top: 0;
  background-color: transparent;
  padding: 10px 24px;
  z-index: 10;
  height: 5vh;
}

.navbar__menu {
  display: flex;
  width: 100%;
  justify-content: space-evenly;
}

.navbar__link {
  color: var(--text-color);
}
</style>
