<script setup lang="ts">
import { ref, computed } from 'vue'

const images = [
    {
        src: 'https://petapixel.com/assets/uploads/2022/12/what-is-unsplash-800x420.jpg',
        alt: 'Image_1',
    },
    {
        src: 'https://petapixel.com/assets/uploads/2022/12/image13-1-800x536.jpg',
        alt: 'Image_2',
    },
    {
        src: 'https://petapixel.com/assets/uploads/2022/12/image11-1-800x534.jpg',
        alt: 'Image_3',
    },
];

const currentSliderIndex = ref(0);
const showModal = ref(false);
const currentImage = computed(() => images[currentSliderIndex.value]);

function openModal() { showModal.value = true; }
function closeModal() { showModal.value = false; }

const nextSlide = () => {
    currentSliderIndex.value = (currentSliderIndex.value + 1) % images.length;
};
const prevSlide = () => {
    currentSliderIndex.value = (currentSliderIndex.value - 1 + images.length) % images.length;
};
</script>

<template>
  <div class="playground">
    <h1>Playground</h1>
    <p>This is your playground. Add your experiments here!</p>
  </div>

   <h2>Image Carousel</h2>
  <div class="carousel">
    <div class="carousel-images">
      <img
        class="carousel-image-list"
        v-for="(image, index) in images"
        :key="index"
        :src="image.src"
        :alt="image.alt"
        v-show="index === currentSliderIndex"
        @click="openModal"
        style="cursor: pointer;"
      />
      <div class="carousel-controls">
        <button class="carousel-arrow" @click="prevSlide">&#8592;</button>
        <button class="carousel-arrow" @click="nextSlide">&#8594;</button>
      </div>
    </div>
    <div v-if="showModal" class="modal-overlay" @click.self="closeModal">
      <div class="modal-content">
        <img :src="currentImage?.src" :alt="currentImage?.alt" class="modal-image" />
        <button class="modal-close" @click="closeModal">&times;</button>
      </div>
    </div>
  </div>

</template>

<style scoped>
.playground {
  max-width: 800px;
  margin: 2rem auto;
  padding: 2rem;
  background: #f9f9f9;
  border-radius: 12px;
  box-shadow: 0 2px 8px rgba(0,0,0,0.07);
  text-align: center;
}

.carousel-images { position: relative; display: inline-block; }
.carousel-image-list { width: 7.5cm; height: 5cm; object-fit: cover; display: block; }
.carousel-controls {
  display: flex; justify-content: space-between; width: 7.5cm; margin-top: 6px;
}
.carousel-arrow {
  background: none; border: none; font-size: 1.5rem;
  cursor: pointer; color: #444; padding: 0 4px; line-height: 1;
}
.carousel-arrow:hover { color: #000; }

.modal-overlay {
  position: fixed; top: 0; left: 0; width: 100vw; height: 100vh;
  background: rgba(0,0,0,0.7); display: flex;
  align-items: center; justify-content: center; z-index: 1000;
}
.modal-content {
  position: relative; background: #fff; border-radius: 8px;
  padding: 16px; box-shadow: 0 2px 16px rgba(0,0,0,0.3);
  max-width: 90vw; max-height: 90vh;
  display: flex; flex-direction: column; align-items: center;
}
.modal-image { max-width: 80vw; max-height: 70vh; border-radius: 8px; object-fit: contain; }
.modal-close {
  position: absolute; top: 8px; right: 12px;
  background: none; border: none; font-size: 2rem; color: #333; cursor: pointer;
}

</style>
