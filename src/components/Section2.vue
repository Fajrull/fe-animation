<script setup>
import { gsap } from 'gsap'
import { ScrollTrigger } from 'gsap/ScrollTrigger'
import { ref, onMounted, nextTick } from 'vue'

gsap.registerPlugin(ScrollTrigger)

onMounted(async () => {
  await nextTick()
  gsap.from(videoRef.value, {
    y: 100,
    opacity: 0,
    duration: 1,
    ease: 'power2.out',
    scrollTrigger: {
      trigger: videoRef.value,
      start: 'top 100%',
      toggleActions: 'play reverse play reverse',
    },
  })
})

const videoRef = ref(null)
</script>

<template>
  <section class="section2">
    <div class="container">
      <h2>We are</h2>
      <div>
        team of like-minded people, socially active companies, media personalities, volunteers who
        help low-income shelters and foster carers to support homeless animals.
      </div>
      <h2>Our primary goal</h2>
      <div>
        is to provide animals with the most necessary things - food, medicine, and urgent needs for
        the livelihood of shelters. We believe in our power and the power of conscious citizens who
        care about the environment and their health, who understand the importance of helping each
        other, especially our little friends. Growth begins with your care for your loved ones.
        Animals are one of the closest creatures to humans who remain with us throughout our lives.
        We all know the healing power of warmth, grace, and big loving eyes.
      </div>
      <blockquote>
        "Animals need to have friends. Just like humans." <br />
        - James Herriot, All Creatures Great and Small
      </blockquote>
      <div>
        Who else if not we should support our younger brothers, especially in difficult times? Let's
        be friends!
      </div>
      <div class="video" ref="videoRef">
        <iframe
          src="https://www.youtube.com/embed/5Wk1rp99B7o?start=12"
          title="YouTube video player"
          frameborder="0"
          allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture"
          allowfullscreen
        ></iframe>
      </div>
    </div>
  </section>
</template>
