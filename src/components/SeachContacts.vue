<script setup>
import ListContacts from "./ListContacts.vue";
import { ref } from "vue";

const bgColor = ref("bg-blue-500 px-5 py-1.5 rounded-xl");

const colorFocus = () => {
  bgColor.value = "bg-red-800 px-5 py-1.5 rounded-xl";
};

const props = defineProps({
  ListContacts: Array,
});

const buscarContacto = () => {
  console.log("Buscando contacto");
};
</script>

<template>
  <div class="flex items-center my-5">
    <input
      autocomplete="username"
      class="block flex-1 rounded-xl mx-5 border-0 bg-slate-200 py-1.5 pl-1 text-white placeholder:text-gray-400 focus:ring-0 sm:text-sm sm:leading-6"
      placeholder="Búsqueda"
      type="text"
      @focus="colorFocus()"
    />
    <button :class="bgColor" @click="buscarContacto()">Buscar</button>
  </div>
</template>
