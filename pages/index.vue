<!-- pages/index.vue -->
<template>
    <div class="container">
      <HeaderView />
      <h2 style="margin-top: 15px">Sitio de Comics</h2>
       <p>Esta web ofrece informacion de comics y sus personajes, revistas e ilustradores.</p>
       <ul>
         <li> <NuxtLink to="/personajes_index">Información de personajes</NuxtLink></li>
         <li> <NuxtLink to="/revistas_index">Información de revistas</NuxtLink></li>
         <li> <NuxtLink to="/ilustradores_index">Información de ilustradores</NuxtLink></li>
       </ul>
      <FooterView />
    </div>
   </template>