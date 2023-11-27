<!-- pages/revistas/[...slug].vue -->
<template>
  <div class="container">
    <HeaderView />
    <div class="row">
      <div class="three columns">
        <img class="u-max-full-width" :src="`https://cms-una.000webhostapp.com/storage/uploads/${obj.image}`">
      </div>
      <div class="six columns">
        <h4>{{ obj.title }}</h4>
        <b>Nombre Real: </b>{{ obj.nombre_real }}<br />
        <b>Poder: </b>{{ obj.poder }}<br />
        <b>Debilidad: </b>{{ obj.debilidad }}<br />
        <b>Cuidad: </b>{{ obj.cuidad }}<br />
        <b>Afinidad: </b>{{ obj.afinidad }}<br /><br />
        <b>Ilustrador: </b>
        <NuxtLink :to="'/ilustradores/' + obj.ilustrador_id">{{ obj.ilustrador_name }}</NuxtLink><br />
        <b>Revista: </b>
        <NuxtLink :to="'/revistas/' + obj.revista_id">{{ obj.revista_name }}</NuxtLink><br />
        <pre></pre>
        <h5>Descripción:</h5>
        <span v-html="obj.descripcion"></span>
      </div>
      <div class="two columns"></div>
    </div>
    <utteranc/>
    <FooterView />
  </div>
</template>
<script setup>
const route = useRoute()
const { data: obj, refresh } =
  await useFetch(`https://cms-una.000webhostapp.com/api/content/item/Personajes/${route.params.slug}`)
refresh()
</script>