<script setup>
import { teamMembers } from '@/data/teamMembers'
import gsap from 'gsap'
import { ScrollTrigger } from 'gsap/ScrollTrigger'
import { nextTick, onMounted } from 'vue'

gsap.registerPlugin(ScrollTrigger)

onMounted(async () => {
  await nextTick()
  const teams = document.querySelectorAll('.card-team')
  teams.forEach((team) => {
    gsap.from(team, {
      y: 100,
      opacity: 0,
      duration: 1,
      ease: 'power2.out',
      scrollTrigger: {
        trigger: team,
        start: 'top 90%',
        end: 'bottom 10%',
        toggleActions: 'play reverse play reverse',
      },
    })
  })
})
</script>

<template>
  <section class="section5">
    <div class="container5">
      <h2>Our team</h2>
      <div style="margin-bottom: 2rem">
        consists of completely different people who are united by a common desire - to help
      </div>
      <div class="team-wrap">
        <main v-for="(member, index) in teamMembers" :key="index" class="card-team">
          <div class="team-items">
            <div class="team-item">
              <img :src="member.img" class="team-img" />
              <p style="margin-bottom: 1rem">{{ member.name }}</p>
              <p>{{ member.title }}</p>
            </div>
          </div>
        </main>
      </div>
    </div>
  </section>
</template>
