<template>
  <div class="relative bg-image">
    <div class="absolute top-[50%] translate-y-[-50%] left-0">
      <img src="@/assets/images/flower-save-the-date.png" alt="flower" />
    </div>
    <div class="px-8 py-12 text-center">
      <p class="text-2xl font-semibold tracking-wider uppercase">Chúng mình kết hôn!</p>
      <p class="text-4xl font-signature my-3">Save the date</p>
      <p class="text-4xl font-cormorant-infant font-medium mb-6">
        {{ guest === 'groom' ? '07.12.2025' : '07.12.2025' }}
      </p>
      <div class="w-full h-[250px] overflow-hidden rounded-s-md" style="aspect-ratio: 4/3; background-color: #fff;">
        <img
          src="@/assets/images/save-the-date.webp"
          alt="Ảnh cưới của cặp đôi"
          class="w-full h-full object-cover object-[80%_20%]"
        />
      </div>
    </div>
  </div>
</template>

<script setup lang="ts">
  import { useRoute } from 'vue-router'
  const route = useRoute()
  const guest = route.query.guest as string
</script>

<style lang="scss" scoped>
  .bg-image {
    background-image: url('@/assets/images/bg-save-the-date.jpg');
    background-size: cover;
    background-position: center;
    background-repeat: no-repeat;
  }
</style>
