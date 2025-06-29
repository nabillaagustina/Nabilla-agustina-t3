<template>
  <carousel :autoplay="true" :loop="true" :navigationEnabled="false" :paginationEnabled="true" class="rounded-lg overflow-hidden">
    <slide>
      <img src="./assets/parfum.jpg" alt="Promo Parfum" class="h-64 w-full object-cover" />
    </slide>
    <slide>
      <img src="./assets/kacamata.jpg" alt="Promo Kacamata" class="h-64 w-full object-cover" />
    </slide>
    <slide>
      <img src="./assets/headphone.jpg" alt="Promo Headphone" class="h-64 w-full object-cover" />
    </slide>
  </carousel>
</template>

<script setup>
import { Carousel, Slide } from 'vue3-carousel'
import 'vue3-carousel/dist/carousel.css'
</script>

