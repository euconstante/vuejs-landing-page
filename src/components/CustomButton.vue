<script lang="ts">
import { defineComponent } from 'vue'

import '../assets/styles/buttons.css' // Import your button styles here

export default defineComponent({
  props: {
    href: String,
    target: String,
    primary: Boolean,
    secondary: Boolean,
    buttonName: String,
  },
  computed: {
    blockName() {
      return 'button' // Block name
    },
    isPrimary() {
      return this.primary || false
    },
    isSecondary() {
      return this.secondary || false
    },
  },
  methods: {
    handleClick() {
      this.$emit('click')
    },
  },
})
</script>

<template>
  <a
    :class="[blockName, { 'button--primary': isPrimary, 'button--secondary': isSecondary }, $attrs.class]"
    :href="href"
    :target="target"
  >
    {{ buttonName }}
  </a>
</template>

<style></style>
