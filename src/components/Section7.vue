<script setup>
import { onMounted, nextTick } from 'vue'
import gsap from 'gsap'
import { ScrollTrigger } from 'gsap/ScrollTrigger'
gsap.registerPlugin(ScrollTrigger)

onMounted(async () => {
  await nextTick()
  const teams = document.querySelectorAll('.partner-img')
  teams.forEach((partner) => {
    gsap.from(partner, {
      y: 100,
      opacity: 0,
      duration: 1,
      ease: 'power2.out',
      scrollTrigger: {
        trigger: partner,
        start: 'top 90%',
        end: 'bottom 10%',
        toggleActions: 'play reverse play reverse',
      },
    })
  })
})
</script>

<template>
  <section class="section7">
    <div class="container7">
      <div>
        <h2>Our partners</h2>
        <div style="margin-bottom: 2rem">
          are take care of our fund and help us with many questions
        </div>
      </div>
      <div class="partner-wrap">
        <div class="partner-img">
          <img src="../assets/images/partner1.jpg" alt="" />
        </div>
        <div class="partner-img">
          <img src="../assets/images/partner2.png" alt="" />
        </div>
        <div class="partner-img">
          <img src="../assets/images/partner3.png" alt="" />
        </div>
        <div class="partner-img">
          <img src="../assets/images/partner4.png" alt="" />
        </div>
        <div class="partner-img">
          <img src="../assets/images/partner5.png" alt="" />
        </div>
        <div class="partner-img">
          <img src="../assets/images/partner6.jpeg" alt="" />
        </div>
      </div>
    </div>
  </section>
</template>
