<script setup>
import { helpTitles } from '../data/helpTitles'
import gsap from 'gsap'
import { ScrollTrigger } from 'gsap/ScrollTrigger'
import { onMounted } from 'vue'

gsap.registerPlugin(ScrollTrigger)

onMounted(() => {})
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
    </div>
  </section>
</template>
