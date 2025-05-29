<script setup>
import { supportUs } from '@/data/supportUs'
import gsap from 'gsap'
import { ScrollTrigger } from 'gsap/ScrollTrigger'
import { nextTick, onMounted } from 'vue'

gsap.registerPlugin(ScrollTrigger)

onMounted(async () => {
  await nextTick()
  const teams = document.querySelectorAll('.support-team')
  teams.forEach((support) => {
    gsap.from(support, {
      y: 100,
      opacity: 0,
      duration: 1,
      ease: 'power2.out',
      scrollTrigger: {
        trigger: support,
        start: 'top 90%',
        end: 'bottom 10%',
        toggleActions: 'play reverse play reverse',
      },
    })
  })
})
</script>

<template>
  <section class="section6">
    <div class="container6">
      <h2>Socially active citizens</h2>
      <div style="margin-bottom: 2rem">support us</div>

      <div class="support-wrap">
        <main v-for="(member, index) in supportUs" :key="index" class="support-team">
          <div class="support-items">
            <div class="support-item">
              <img :src="member.img" class="support-img" />
              <p class="title">{{ member.name }}</p>
              <p class="subtitle">{{ member.title }}</p>
            </div>
          </div>
        </main>
      </div>
    </div>
  </section>
</template>
