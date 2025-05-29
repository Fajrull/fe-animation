<script setup>
import gsap from 'gsap'
import ScrollTrigger from 'gsap/ScrollTrigger'
import { onMounted, ref } from 'vue'

gsap.registerPlugin(ScrollTrigger)

const hero1 = ref(null)
const hero2 = ref(null)
const headerTitle = ref(null)
const headerSubtitle = ref(null)
const headerSocials = ref(null)

onMounted(() => {
  gsap.set([hero1.value, hero2.value], { y: -200, opacity: 0 })

  const tl = gsap.timeline({ repeat: -1 })

  tl.to(hero1.value, { y: 0, opacity: 1, duration: 0.3 }).to(hero1.value, {
    y: 100,
    opacity: 0,
    duration: 0.3,
    delay: 1,
  })

  tl.to(hero2.value, { y: 0, opacity: 1, duration: 0.3 }).to(hero2.value, {
    y: 100,
    opacity: 0,
    delay: 1,
    duration: 0.3,
  })

  gsap.set(headerTitle.value, { x: 200, opacity: 0 })
  gsap.set(headerSubtitle.value, { y: 100, opacity: 0 })
  gsap.set(headerSocials.value, { y: 100, opacity: 0 })

  gsap.to(headerTitle.value, {
    scrollTrigger: {
      trigger: headerTitle.value,
      start: 'top 80%',
      end: 'bottom 20%',
      toggleActions: 'play reverse play reverse',
    },
    x: 0,
    opacity: 1,
    duration: 1,
    ease: 'power3.out',
  })

  gsap.to(headerSubtitle.value, {
    scrollTrigger: {
      trigger: headerSubtitle.value,
      start: 'top 90%',
      end: 'bottom 10%',
      toggleActions: 'play reverse play reverse',
    },
    y: 0,
    opacity: 1,
    duration: 1,
    ease: 'power3.out',
    delay: 0.3,
  })

  gsap.to(headerSocials.value, {
    scrollTrigger: {
      trigger: headerSocials.value,
      start: 'top 90%',
      end: 'bottom 10%',
      toggleActions: 'play reverse play reverse',
    },
    y: 0,
    opacity: 1,
    duration: 1,
    ease: 'power3.out',
    delay: 0.3,
  })
})
</script>

<template>
  <header class="header">
    <div class="header-container">
      <div>
        <button class="header-button">donate</button>
      </div>
      <div>
        <button class="header-webflow">
          <img src="../assets/images/webflow.svg" alt="" />
          Made in Webflow
        </button>
      </div>
      <div class="header-content">
        <div class="hero-container">
          <img
            ref="hero1"
            src="../assets/images/hero.svg"
            alt="hero"
            class="hero hero1"
            loading="lazy"
          />
          <img
            ref="hero2"
            src="../assets/images/hero2.svg"
            alt="hero"
            class="hero hero2"
            loading="lazy"
          />
        </div>
        <h1 class="header-title" ref="headerTitle">
          Innovative <br />
          Solutions <br />
          for <br />
          Animals
        </h1>
      </div>
      <div class="header-subtitle" ref="headerSubtitle">charity organization</div>
    </div>

    <div class="header-socials" ref="headerSocials">
      <img src="../assets/images/yt.svg" alt="icon" class="social-icon" />
      <img src="../assets/images/ig.svg" alt="icon" class="social-icon" />
      <img src="../assets/images/fb.svg" alt="icon" class="social-icon" />
      <img src="../assets/images/io.svg" alt="icon" class="social-icon" />
      <img src="../assets/images/tele.svg" alt="icon" class="social-icon" />
    </div>
  </header>
</template>
