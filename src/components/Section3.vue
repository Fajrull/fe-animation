<script setup>
import gsap from 'gsap'
import { onMounted, ref } from 'vue'
import { ScrollTrigger } from 'gsap/ScrollTrigger'

const project1 = ref(null)
const project2 = ref(null)
const project3 = ref(null)

gsap.registerPlugin(ScrollTrigger)

onMounted(() => {
  const animateItem = (element) => {
    gsap.fromTo(
      element,
      { x: -100, opacity: 0 },
      {
        x: 0,
        opacity: 1,
        duration: 0.8,
        ease: 'power2.out',
        scrollTrigger: {
          trigger: element,
          start: 'top 80%',
          end: 'bottom 20%',
          toggleActions: 'play reverse play reverse',
        },
      },
    )
  }

  animateItem(project1.value)
  animateItem(project2.value)
  animateItem(project3.value)
})
</script>

<template>
  <section class="section3">
    <div class="container3">
      <h2>Our projects</h2>
      <div>are very different in terms of priority, scale and complexity of implementation</div>

      <div class="project-wrap" ref="project1">
        <div class="project-item">
          <div class="project-title">Emergency Aid. WAR 2022.</div>
          <p>
            providing food and medicine to the shelters and animals which lost their homes and
            families due to the war
          </p>
        </div>
      </div>

      <div class="project-wrap2" ref="project2">
        <div class="project-item">
          <div class="project-title">Non-commercial feed line</div>
          <p>
            construction of industrial production base where food for shelters will be produced on a
            free basis
          </p>
        </div>
      </div>

      <div class="project-wrap3" ref="project3">
        <div class="project-item">
          <div class="project-title">Education and Control</div>
          <p>
            lectures on communication, organisation and coordination of processes, control over the
            use of aid
          </p>
        </div>
      </div>
    </div>
  </section>
</template>
