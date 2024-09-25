<script setup>
import { ref } from "vue";

import SeachContacts from "./components/SeachContacts.vue";
import ListContacts from "./components/ListContacts.vue";
//
import { getAllContacts } from "./services/apiContacts";
//
const listContacts = ref(getAllContacts());

const title = "MI AGENDA - Lista de contactos";

const clearList = () => {
  listContacts.value = [];
};
</script>

<template>
  <div class="flex items-center flex-col p-5">
    <h1 class="text-xl m-4">{{ title }}</h1>
    <seach-contacts :listContacts="listContacts" />
    <list-contacts
      title="Resultados de la búsqueda"
      :listContacts="listContacts"
    />
    <div>
      <button class="bg-blue-500 py1.5 px5" @click="clearList">Limpiar</button>
    </div>
  </div>
</template>
