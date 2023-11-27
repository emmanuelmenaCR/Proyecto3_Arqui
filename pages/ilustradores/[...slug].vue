<template>
  <div class="container">
    <HeaderView />
    <div class="row">
      <div class="three columns">
        <img class="u-max-full-width" :src="`https://cms-una.000webhostapp.com/storage/uploads/${obj.image}`">
      </div>
      <div class="six columns">
        <h4>{{ obj.title }}</h4>
        <b>Nacionalidad: </b>{{ obj.nacionalidad }}<br />
        <b>Fecha de nacimiento: </b>{{ obj.fecha_nacimiento }} <br />
        <b>Sexo: </b>{{ obj.sexo }}; <br />
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
  await useFetch(`https://cms-una.000webhostapp.com/api/content/item/Ilustradores/${route.params.slug}`)
refresh()
</script>