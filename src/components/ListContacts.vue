<script setup>
const props = defineProps({
  title: String,
  listContacts: {
    type: Array,
    default: [],
  },
});
</script>

<template>
  <div class="m-6">
    <h3 class="text-xl my-3">{{ title }}</h3>
    <table class="table-fixed">
      <thead>
        <tr>
          <th>Foto</th>
          <th>Nombres</th>
          <th>Número</th>
          <th>Correo</th>
          <th>Acción</th>
        </tr>
      </thead>
      <tbody>
        <tr v-for="contact in listContacts">
          <td class="p-3 border-b-2">{{ contact.id }}</td>
          <td class="p-3 border-b-2">{{ contact.name }}</td>
          <td class="p-3 border-b-2">{{ contact.phone }}</td>
          <td class="p-3 border-b-2">{{ contact.email }}</td>
          <td>
            <a href="#" class="py-2 px-4 bg-purple-800 rounded-full">Editar</a>
          </td>
        </tr>
      </tbody>
    </table>
  </div>
</template>
