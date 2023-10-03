<script>
import Card from '@/components/Card.vue'
import { reasonsList } from '@/constants'

export default {
  components: {
    Card,
  },
  data() {
    return {
      topTen: reasonsList,
      currentIndex: 0,
      cardsToShow: 2,
    }
  },
  computed: {
    visibleCards() {
      return this.topTen.slice(this.currentIndex, this.currentIndex + this.cardsToShow)
    },
  },
  methods: {
    showNext() {
      if (this.currentIndex + this.cardsToShow < this.topTen.length) {
        this.currentIndex += this.cardsToShow
      }
    },
    showPrevious() {
      if (this.currentIndex > 0) {
        this.currentIndex -= this.cardsToShow
      }
    },
    updateCardsToShow() {
      if (window.innerWidth >= 1400) {
        this.cardsToShow = 3
      } else if (window.innerWidth >= 800) {
        this.cardsToShow = 2
      } else {
        this.cardsToShow = 1
      }
    },
  },
  mounted() {
    this.updateCardsToShow()
    window.addEventListener('resize', this.updateCardsToShow)
  },
  beforeDestroy() {
    window.removeEventListener('resize', this.updateCardsToShow)
  },
}
</script>

<template>
  <div class="card__catalog">
    <transition name="slide-fade" mode="out-in">
      <div class="card__slide__container" :key="currentIndex">
        <Card
          v-for="(card, index) in visibleCards"
          :key="index"
          :title="card.title"
          :subtitle="card.subtitle"
          :description="card.description"
          :rank="card.rank"
        />
      </div>
    </transition>
    <button @click="showPrevious" class="arrow__button prev" :disabled="currentIndex === 0">&#8592;</button>
    <button @click="showNext" class="arrow__button next" :disabled="currentIndex + cardsToShow >= topTen.length">
      &#8594;
    </button>
  </div>
</template>

<style scoped>
.card__catalog {
  position: relative;
  overflow: hidden;
  padding-top: 3rem;
}

.card__slide__container {
  display: flex;
  justify-content: center;
  margin-left: 5rem;
}

.arrow__button {
  position: absolute;
  top: 50%;
  transform: translateY(-50%);
  background-color: transparent;
  border: none;
  font-size: 2.5rem;
  cursor: pointer;
  z-index: 100;
  color: rgba(255, 255, 255, 0.593);

  padding: 12rem 2rem;
}
.arrow__button:hover {
  color: rgba(6, 13, 23, 0.8);
  background: rgba(255, 255, 255, 0.593);
}
.next {
  right: 0px;
}

.prev {
  left: -10px;
}

.slide-fade-enter-active {
  transition: 0.1s;
}

.slide-fade-enter-from,
.slide-fade-leave-to {
  transform: translateX(90%);
  opacity: 0;
  transition: 0.2s;
}

@media (max-width: 600px) {
  .card__slide__container {
    margin-left: 0;
  }
}
</style>
