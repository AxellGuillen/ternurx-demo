<script setup>
import { ref, watch } from "vue";

const props = defineProps({
  imagenes: {
    type: Array,
    required: true,
  },
});

const currentImage = ref(0);

watch(
  () => props.imagenes,
  () => {
    currentImage.value = 0;
  }
);

const nextImage = () => {
  if (props.imagenes.length > 0) {
    currentImage.value = (currentImage.value + 1) % props.imagenes.length;
  }
};

const prevImage = () => {
  if (props.imagenes.length > 0) {
    currentImage.value =
      (currentImage.value - 1 + props.imagenes.length) % props.imagenes.length;
  }
};
</script>

<template>
  <div class="relative min-h-screen">
    <Lista :links="links" @click-project="clickProject" />
    <div
      class="absolute inset-0 flex items-center justify-center"
      style="top: 5%; transform: translateY(-50%)"
    >
      <div v-if="props.imagenes.length > 0" class="relative">
        <img
          :src="props.imagenes[currentImage]"
          alt="imagen del proyecto"
          class="max-w-xl transition duration-300"
        />
        <div class="flex justify-between mt-4 space-x-10">
          <button
            @click="prevImage"
            class="px-4 py-2 font-bold hover:text-pinkish uppercase cursor-crosshair"
          >
            Prev
          </button>
          <button
            @click="nextImage"
            class="px-4 py-2 font-bold hover:text-pinkish uppercase cursor-crosshair"
          >
            Next
          </button>
        </div>
      </div>
      <div v-else class="text-gray-400"></div>
    </div>
  </div>
</template>
