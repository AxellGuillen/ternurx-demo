<script setup>
import Navbar from "./components/Navbar.vue";
import Footer from "./components/Footer.vue";
import Lista from "./components/Lista.vue";
import Galeria from "./components/Galeria.vue";

import img1 from "./assets/imagenes/img1.jpg";
import img2 from "./assets/imagenes/img2.jpg";
import img3 from "./assets/imagenes/img3.jpg";
import img4 from "./assets/imagenes/img4.jpg";
import img5 from "./assets/imagenes/img5.jpg";

import { ref } from "vue";

const links = ref([
  {
    label: "AW25",
    path: "/ssw",
    imagenes: [img1, img2, img3],
  },
  {
    label: "AW24",
    path: "/ssw23",
    imagenes: [img4, img5],
  },
  {
    label: "AW23",
    path: "/ssw23",
    imagenes: [img1, img2, img3],
  },
  {
    label: "AW22",
    path: "/ssw23",
    imagenes: [img1, img2, img3],
  },
  {
    label: "AW21",
    path: "/ssw23",
    imagenes: [img1, img2, img3],
  },
  {
    label: "AW20",
    path: "/ssw23",
    imagenes: [img1, img2, img3],
  },
  {
    label: "AW19",
    path: "/ssw23",
    imagenes: [img1, img2, img3],
  },
]);

const projectState = ref(null);

const clickProject = (project) => {
  projectState.value = project.imagenes;
};
</script>

<template>
  <div>
    <Navbar />
    <Lista :links="links" @click-project="clickProject" />
    <Galeria :imagenes="projectState || []" />
    <Footer />
  </div>
</template>
