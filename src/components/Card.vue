<template>
  <div class="border rounded-xl overflow-hidden shadow hover:shadow-lg transition-shadow bg-white text-gray-800">
    <img :src="img" alt="Gambar {{ title }}" class="w-full h-48 object-cover" />
    <div class="p-4">
      <h3 class="font-semibold text-lg mb-1">{{ title }}</h3>
      <p class="text-sm text-gray-600">{{ desc }}</p>
    </div>
  </div>
</template>

<script setup>
defineProps({
  title: String,
  desc: String,
  img: String,
})
</script>
