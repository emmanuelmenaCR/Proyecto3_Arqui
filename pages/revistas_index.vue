<!-- pages/publishers_index.vue -->
<template>
  <div class="container">
    <HeaderView />
    <h3 style="margin-top: 15px">Página de revistas</h3>
    <p>En esta sección tenemos las diferentes revistas.</p>
    <ul>
      <li v-for="obj in objs" :key="obj._id">
        <NuxtLink :to="`/revistas/` + obj._id">{{ obj.title }}</NuxtLink>
      </li>
    </ul>
    <FooterView />
  </div>
</template>
<script setup>
const { data: objs } =
  await useFetch(`https://cms-una.000webhostapp.com/api/content/items/Revistas?fields={'title':true}`)
</script>