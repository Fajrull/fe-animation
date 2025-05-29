<script setup>
import { gsap } from 'gsap'
import { ScrollTrigger } from 'gsap/ScrollTrigger'
import { onMounted, nextTick, ref } from 'vue'

gsap.registerPlugin(ScrollTrigger)
const footerIcon = ref(null)

onMounted(async () => {
  await nextTick()
  gsap.from(footerIcon.value, {
    y: 100,
    opacity: 0,
    duration: 1,
    ease: 'power2.out',
    scrollTrigger: {
      trigger: footerIcon.value,
      start: 'top 100%',
      toggleActions: 'play reverse play reverse',
    },
  })
})
</script>

<template>
  <footer class="footer">
    <div class="footer-left">
      <h2>Contact us</h2>
      <div>Kyiv, Ukraine</div>
      <div>mail@isa.co.ua</div>
      <div class="footer-socials">
        <img src="../assets/images/yt.svg" alt="icon" class="footer-icon" />
        <img src="../assets/images/ig.svg" alt="icon" class="footer-icon" />
        <img src="../assets/images/fb.svg" alt="icon" class="footer-icon" />
        <img src="../assets/images/io.svg" alt="icon" class="footer-icon" />
        <img src="../assets/images/tele.svg" alt="icon" class="footer-icon" />
      </div>
    </div>
    <div class="footer-right" ref="footerIcon">
      <img src="../assets//images/footer.svg" alt="" />
    </div>
  </footer>
</template>
