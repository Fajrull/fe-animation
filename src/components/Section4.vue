<script setup>
import { helpTitles } from '../data/helpTitles'
import gsap from 'gsap'
import { ScrollTrigger } from 'gsap/ScrollTrigger'
import { onMounted } from 'vue'

gsap.registerPlugin(ScrollTrigger)

onMounted(() => {
  const items = document.querySelectorAll('.help-bg')
  items.forEach((item) => {
    gsap.from(item, {
      y: 100,
      opacity: 0,
      duration: 1,
      ease: 'power2.out',
      scrollTrigger: {
        trigger: item,
        start: 'top 90%',
        end: 'bottom 10%',
        toggleActions: 'play reverse play reverse',
        // markers: true,
      },
    })
  })

  const applyHelp = document.querySelector('.apply-help')
  gsap.from(applyHelp, {
    x: -100,
    opacity: 0,
    duration: 1,
    ease: 'power2.out',
    scrollTrigger: {
      trigger: applyHelp,
      start: 'top 80%',
      end: 'bottom 20%',
      toggleActions: 'play reverse play reverse',
    },
  })
})
</script>

<template>
  <section class="section4">
    <div class="container4">
      <h2>We want to help</h2>
      <div>
        homeless packs, volunteers, guardians, overstayers, shelters and other organisations
      </div>
      <div class="help-wrap">
        <div class="help-bg" v-for="(title, index) in helpTitles" :key="index">
          <div class="help-item">
            <p class="help-title">{{ title }}</p>
          </div>
        </div>
      </div>
      <div class="apply-help">
        apply for help
        <img src="../assets/images/arrow.png" alt="arrow" />
      </div>
    </div>
  </section>
</template>
