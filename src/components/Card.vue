<script>
export default {
  props: {
    title: String,
    subtitle: String,
    description: String,
    rank: Number,
  },
}
</script>

<template>
  <transition name="card-slide" mode="out-in">
    <div class="card-container">
      <div class="card__details hide">
        <div class="card__rank">{{ rank }}</div>
      </div>
      <div class="card">
        <p class="card__subtitle subtitle--small">{{ subtitle }}</p>
        <h3 class="card__title title--small">{{ title }}</h3>
        <p class="card__description description">{{ description }}</p>
      </div>
    </div>
  </transition>
</template>

<style scoped>
.card-slide-enter-active,
.card-slide-leave-active {
  transition: transform 0.8s;
}
.card-slide-enter,
.card-slide-leave-to {
  transform: translateX(100%);
}

.card-container {
  display: flex;
  align-items: flex-end;
}

.card {
  display: flex;
  flex-direction: column;
  align-items: center;
  justify-content: space-evenly;
  width: 18rem;
  margin: 0 3.125rem;
  padding: 2rem 1.5rem;
  background: linear-gradient(180deg, #11181f, rgba(17, 24, 31, 0));
  border-radius: 1rem;
  text-align: center;
  height: 21.875rem;
}

.card__subtitle {
  color: var(--primary-color);
  text-transform: uppercase;
  padding-top: 1rem;
}
.card__title {
  padding-top: 1rem;
  padding-bottom: 1rem;
}
.card__description {
  color: var(--text-color-light);
  width: 80%;
  line-height: 1.2rem;
}

.card__details {
  position: absolute;
  margin-left: -3rem;
}
.card__rank {
  font-size: 9.3rem;
  z-index: -1;
  font-weight: 900;
  color: var(--text-color-medium);
}
</style>
