<script setup>
import gsap from 'gsap'
import { onMounted } from 'vue'
import { ref } from 'vue'

const hero1 = ref(null)
const hero2 = ref(null)
const header = ref(null)
const headerTitle = ref(null)
const headerSubtitle = ref(null)
const headerSocials = ref(null)

onMounted(() => {
  gsap.set(hero1.value, { y: -100, opacity: 0 })
  gsap.set(hero2.value, { y: -100, opacity: 0 })

  const tl = gsap.timeline({
    repeat: -1,
  })
  tl.to(hero1.value, {
    y: 0,
    opacity: 1,
    duration: 0.3,
  }).to(hero1.value, {
    y: 100,
    opacity: 0,
    duration: 0.3,
    delay: 1,
  })
  tl.to(hero2.value, {
    y: 0,
    opacity: 4,
    duration: 0.3,
  }).to(hero2.value, {
    y: 100,
    opacity: 0,
    delay: 1,
    duration: 0.3,
  })
})
</script>

<template>
  <header class="header">
    <div class="header-container">
      <div>
        <button class="header-button">donate</button>
      </div>
      <div class="header-content">
        <div class="hero-container">
          <img ref="hero1" src="../assets/images/hero.svg" alt="hero" class="hero hero1" />
          <img ref="hero2" src="../assets/images/hero2.svg" alt="hero" class="hero hero2" />
        </div>
        <h1 class="header-title">
          Innovative <br />
          Solutions <br />
          for <br />
          Animals
        </h1>
      </div>
      <div class="header-subtitle">charity organization</div>
    </div>
    <div class="header-socials">
      <img src="../assets/images/yt.svg" alt="icon" class="social-icon" />
      <img src="../assets/images/ig.svg" alt="icon" class="social-icon" />
      <img src="../assets/images/fb.svg" alt="icon" class="social-icon" />
      <img src="../assets/images/io.svg" alt="icon" class="social-icon" />
      <img src="../assets/images/tele.svg" alt="icon" class="social-icon" />
    </div>
  </header>
</template>

<style scoped></style>
