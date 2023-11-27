<!-- pages/publishers_index.vue -->
<template>
  <div class="container">
    <HeaderView />
    <h3 style="margin-top: 15px">Página de ilustradores</h3>
    <p>En esta sección tenemos los diferentes ilustradores.</p>
    <ul>
      <li v-for="obj in objs" :key="obj._id">
        <NuxtLink :to="`/ilustradores/` + obj._id">{{ obj.title }}</NuxtLink>
      </li>
    </ul>
    <FooterView />
  </div>
</template>
<script setup>
const { data: objs } =
  await useFetch(`https://cms-una.000webhostapp.com/api/content/items/Ilustradores?fields={'title':true}`)
</script>