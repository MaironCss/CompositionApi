<script setup lang="ts">
// import { RouterLink, RouterView } from 'vue-router'
// import { ref } from 'vue'
import HeaderSection from './components/headerSection.vue'
import noveltySection from './components/noveltySection.vue'
import newArrivalSection from './components/newArrivalSection.vue'
import collectionsSection from './components/collectionsSection.vue'
import thoughtSection from './components/thoughtSection.vue'
import blogSection from './components/blogSection.vue'
import contactSection from './components/contactSection.vue'
import { arrivalsArr } from './constants'
import type { ArrivalItem } from './types/ArrivalType'
import { ref } from 'vue'

let arrivals = ref(arrivalsArr)

function showDetails(item: ArrivalItem): void {
  console.log('item', item)
}
</script>

<template>
  <HeaderSection />
  <noveltySection />
  <newArrivalSection :newArrivals="arrivals" @show-details="showDetails($event)" />
  <collectionsSection />
  <thoughtSection />
  <blogSection />
  <contactSection />
</template>

<style scoped></style>
