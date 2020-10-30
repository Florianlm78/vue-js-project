<template>
  <div class="text-center">
      Votre panier : {{selection.length}}
  </div>
  <div class="border-gray-500 padding p-8">
        <p class="text-center border-gray-500" v-for="album in selection" :key="album.name">{{album.name}} | {{album.artiste}} | {{album.prix}}€</p>
  </div>
  
</template>

<script>
export default {
    name: "selection-box",
    props:['selection'],
    computed: {
        
    }

}
</script>

<style>

</style>