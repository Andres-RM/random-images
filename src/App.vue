<script setup lang="ts">
import { ref, onMounted } from "vue";

const images = ref<string[]>([]);
const currentImage = ref<string>("");

const loadImages = () => {
  images.value = [
    "/images/" + encodeURIComponent("RESPUESTAS DEL UNIVERSO_page-0001.png"),
    "/images/" + encodeURIComponent("RESPUESTAS DEL UNIVERSO_page-0003.png"),
    "/images/" + encodeURIComponent("RESPUESTAS DEL UNIVERSO_page-0005.png"),
    "/images/" + encodeURIComponent("RESPUESTAS DEL UNIVERSO_page-0007.png"),
    "/images/" + encodeURIComponent("RESPUESTAS DEL UNIVERSO_page-0009.png"),
    "/images/" + encodeURIComponent("RESPUESTAS DEL UNIVERSO_page-0011.png"),
    "/images/" + encodeURIComponent("RESPUESTAS DEL UNIVERSO_page-0013.png"),
    "/images/" + encodeURIComponent("RESPUESTAS DEL UNIVERSO_page-0015.png"),
    "/images/" + encodeURIComponent("RESPUESTAS DEL UNIVERSO_page-0017.png"),
    "/images/" + encodeURIComponent("RESPUESTAS DEL UNIVERSO_page-0019.png"),
    "/images/" + encodeURIComponent("RESPUESTAS DEL UNIVERSO_page-0021.png"),
    "/images/" + encodeURIComponent("RESPUESTAS DEL UNIVERSO_page-0023.png"),
    "/images/" + encodeURIComponent("RESPUESTAS DEL UNIVERSO_page-0025.png"),
    "/images/" + encodeURIComponent("RESPUESTAS DEL UNIVERSO_page-0027.png"),
    "/images/" + encodeURIComponent("RESPUESTAS DEL UNIVERSO_page-0029.png"),
    "/images/" + encodeURIComponent("RESPUESTAS DEL UNIVERSO_page-0031.png"),
    "/images/" + encodeURIComponent("RESPUESTAS DEL UNIVERSO_page-0033.png"),
    "/images/" + encodeURIComponent("RESPUESTAS DEL UNIVERSO_page-0035.png"),
    "/images/" + encodeURIComponent("RESPUESTAS DEL UNIVERSO_page-0037.png"),
    "/images/" + encodeURIComponent("RESPUESTAS DEL UNIVERSO_page-0039.png"),
    "/images/" + encodeURIComponent("RESPUESTAS DEL UNIVERSO_page-0041.png"),
    "/images/" + encodeURIComponent("RESPUESTAS DEL UNIVERSO_page-0043.png"),
    "/images/" + encodeURIComponent("RESPUESTAS DEL UNIVERSO_page-0045.png"),
    "/images/" + encodeURIComponent("RESPUESTAS DEL UNIVERSO_page-0047.png"),
    "/images/" + encodeURIComponent("RESPUESTAS DEL UNIVERSO_page-0049.png"),
    "/images/" + encodeURIComponent("RESPUESTAS DEL UNIVERSO_page-0051.png"),
    "/images/" + encodeURIComponent("RESPUESTAS DEL UNIVERSO_page-0053.png"),
    "/images/" + encodeURIComponent("RESPUESTAS DEL UNIVERSO_page-0055.png"),
    "/images/" + encodeURIComponent("RESPUESTAS DEL UNIVERSO_page-0057.png"),
    "/images/" + encodeURIComponent("RESPUESTAS DEL UNIVERSO_page-0059.png"),
    "/images/" + encodeURIComponent("RESPUESTAS DEL UNIVERSO_page-0061.png"),
    "/images/" + encodeURIComponent("RESPUESTAS DEL UNIVERSO_page-0063.png"),
    "/images/" + encodeURIComponent("RESPUESTAS DEL UNIVERSO_page-0065.png"),
    "/images/" + encodeURIComponent("RESPUESTAS DEL UNIVERSO_page-0067.png"),
    "/images/" + encodeURIComponent("RESPUESTAS DEL UNIVERSO_page-0069.png"),
    "/images/" + encodeURIComponent("RESPUESTAS DEL UNIVERSO_page-0071.png"),
    "/images/" + encodeURIComponent("RESPUESTAS DEL UNIVERSO_page-0073.png"),
    "/images/" + encodeURIComponent("RESPUESTAS DEL UNIVERSO_page-0075.png"),
    "/images/" + encodeURIComponent("RESPUESTAS DEL UNIVERSO_page-0077.png")
  ];
};

const getRandomImage = () => {
  if (images.value.length === 0) return;
  const randomIndex = Math.floor(Math.random() * images.value.length);
  currentImage.value = images.value[randomIndex];
};

onMounted(() => {
  loadImages();
  getRandomImage();
});
</script>

<template>
  <main class="page">
    <div class="container mx-auto px-4">
      <div class="flex flex-col py-14 items-center justify-center">

        <div class="mt-8 w-full max-w-2xl flex flex-col items-center">
          <div
            v-if="currentImage"
            class="aspect-square max-w-[500px] relative overflow-hidden rounded-lg shadow-xl bg-neutral-300 p-2 border-primary border"
          >
            <img
              :src="currentImage"
              :alt="'Random image'"
              class="w-full h-full object-contain object-center transition-opacity duration-300"
            />
          </div>
        </div>
      </div>
    </div>
  </main>
</template>

<style scoped>
.aspect-video {
  aspect-ratio: 16 / 9;
}
</style>
