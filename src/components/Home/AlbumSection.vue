<template>
  <section class="bg-primary py-8 px-4 lazy-section">
    <div class="flex items-center">
      <p class="text-white whitespace-nowrap text-5xl font-great-vibes mr-4">Album của chúng tôi</p>
      <div class="w-full h-[1px] bg-white" />
    </div>
    <p class="text-white my-7">
      Album này ghi lại những khoảnh khắc đẹp nhất trong ngày đặc biệt của chúng tôi - tràn đầy tình
      yêu, niềm vui và những kỷ niệm không thể nào quên.
    </p>

    <template v-for="(item, index) in albumRepresent" :key="item.id">
      <div v-if="index <= 1" class="mb-3 h-72">
        <img
          v-lazy="item.img"
          class="w-full h-full object-cover object-[50%_10%]"
          :alt="`album-image-${item.id}`"
        />
      </div>
    </template>
    <div class="grid grid-cols-2 gap-2">
      <template v-for="(item, index) in albumRepresent" :key="item.id">
        <div v-if="index > 1" :id="`album-${item.id}`" class="h-64">
          <img
            v-lazy="item.img"
            class="w-full h-full object-cover"
            :class="item.className"
            :alt="`album-image-${item.id}`"
          />
        </div>
      </template>
    </div>
  </section>
</template>

<script setup lang="ts">
  import { ref } from 'vue'
  import img1 from '@/assets/images/album_1.jpeg'
  import img2 from '@/assets/images/album_2.jpeg'
  import img3 from '@/assets/images/save-the-date.webp'
  import img4 from '@/assets/images/timeline.jpeg'

  const albumRepresent = ref([
    {
      id: 1,
      img: img1
    },
    {
      id: 2,
      img: img2
    },
    {
      id: 3,
      img: img3
    },
    {
      id: 4,
      img: img4,
      className: 'object-[20%_10%]'
    }
  ])
</script>
