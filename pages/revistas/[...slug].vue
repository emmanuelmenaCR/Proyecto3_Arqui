<!-- pages/revistas/[...slug].vue -->
<template>
    <div class="container">
     <HeaderView />
     <div class="row">      
       <div class="three columns">
        <img class="u-max-full-width" :src="`https://cms-una.000webhostapp.com/storage/uploads/${obj.image}`">
       </div>
       <div class="six columns">
         <h4>{{obj.title}}</h4>
         <b>Editorial: </b>{{ obj.editorial }}<br/>
         <b>Tema: </b>{{obj.tema}} <br/>
         <b>Primera edición: </b>{{obj.primera_publicacion}} <br/>
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
    await useFetch(`https://cms-una.000webhostapp.com/api/content/item/Revistas/${route.params.slug}`)
  refresh()
  </script>