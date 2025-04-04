<script setup>
const links = [
  {
    label: "Tienda",
    path: "/tienda",
  },
  {
    label: "exhibiciones",
    path: "/exhibiciones",
  },
  {
    label: "STATEMENT",
    path: "/STATEMENT",
  },
];
</script>

<template>
  <div class="w-full grid grid-cols-[1fr_auto] p-[5px]">
    <div class="w-full flex flex-row gap-[5px] bg-white">
      <div
        v-for="link in links"
        :key="link.path"
        class="relative flex justify-center items-center text-black py-[25px] px-[20px] transition-colors duration-300 hover:text-pinkish uppercase"
      >
        <p
          class="font-editorial font-bold text-2xl leading-[0px] cursor-crosshair"
        >
          {{ link.label }}
        </p>
      </div>
    </div>
    <p
      class="font-editorial font-bold text-2xl h-full flex items-center px-[30px] bg-white transition-colors duration-300 hover:text-pinkish uppercase cursor-crosshair"
    >
      contacto
    </p>
  </div>
</template>
