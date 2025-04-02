<script setup lang="ts">
import { ref, onMounted } from "vue";

const images = ref<string[]>([]);
const currentImage = ref<string>("");

const loadImages = () => {
  images.value = [
    "/images/RESPUESTAS%20DEL%20UNIVERSO_page-0045.png",
    "/images/RESPUESTAS%20DEL%20UNIVERSO_page-0059.png",
    "/images/RESPUESTAS%20DEL%20UNIVERSO_page-0061.png",
    "/images/RESPUESTAS%20DEL%20UNIVERSO_page-0063.png",
    "/images/RESPUESTAS%20DEL%20UNIVERSO_page-0065.png",
    "/images/RESPUESTAS%20DEL%20UNIVERSO_page-0067.png",
    "/images/RESPUESTAS%20DEL%20UNIVERSO_page-0069.png",
    "/images/RESPUESTAS%20DEL%20UNIVERSO_page-0071.png",
    "/images/RESPUESTAS%20DEL%20UNIVERSO_page-0073.png",
    "/images/RESPUESTAS%20DEL%20UNIVERSO_page-0075.png",
    "/images/RESPUESTAS%20DEL%20UNIVERSO_page-0077.png",
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
      <div class="flex flex-col py-14 items-center">
        <h2
          class="scroll-m-20 text-center pb-2 text-5xl font-semibold tracking-tight transition-colors first:mt-0 italic"
        >
          Random Images
        </h2>

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

          <button
            @click="getRandomImage"
            class="mt-6 inline-flex items-center justify-center rounded-md text-sm font-medium transition-colors focus-visible:outline-none focus-visible:ring-2 focus-visible:ring-ring focus-visible:ring-offset-2 disabled:opacity-50 disabled:pointer-events-none ring-offset-background bg-primary text-primary-foreground hover:bg-primary/90 h-10 px-4 py-2 w-full"
          >
            Generate Random Image
          </button>
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
