<script setup>
const props = defineProps({
  links: {
    type: Object,
    required: true,
  },
});

const emits = defineEmits(["click-project"]);
</script>

<template>
  <ul class="border-gray-300 p-7 mt-10 space-y-10 font-editorial font-semibold">
    <li
      v-for="link in links"
      :key="link.path"
      @click="$emit('click-project', link)"
      class="w-fit transition-colors duration-300 hover:text-pinkish cursor-crosshair"
    >
      {{ link.label }}
    </li>
  </ul>
</template>
