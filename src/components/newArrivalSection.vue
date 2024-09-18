<script setup lang="ts">
import type { ArrivalItem } from '../types/ArrivalType'
import { defineProps, defineEmits } from 'vue'

interface Props {
  newArrivals: Array<ArrivalItem>
}
defineProps<Props>()

const emit = defineEmits(['showDetails'])

function showDetails(item: object): void {
  emit('showDetails', item)
}
</script>
<template>
  <section class="arrivals">
    <div class="container">
      <h2 class="arrivals__tagline">Popular Arrivals</h2>
      <div class="arrivals__models">
        <div v-for="item in newArrivals" :key="item.id" class="arrivals__items">
          <div class="wrapper">
            <img src="../assets/img/nike2.png" alt="" />
            <div class="arrivals__details">
              <a @click="showDetails(item)">View Details</a>
            </div>
          </div>
          <h3 class="arrivals__name">
            {{ item.shoesName }}
            <span v-if="item.isOutdoors"> Shop Outdoors</span>
          </h3>
          <p v-if="!item.isOutdoors" class="arrivals__price">
            {{ item.price }}
          </p>
        </div>
      </div>
    </div>
  </section>
</template>

<style scoped>
.arrivals__items {
  margin-left: 8px;
}
</style>
