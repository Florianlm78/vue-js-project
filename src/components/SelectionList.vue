<template>
  <div class="container w-4/5 mx-auto mt-4">
    <h1 class="text-lg font-bold">Ma sélection</h1>

    <div v-if="selection.length == 0">
      <p>Aucun album sélectionné</p>
    </div>
    <div else>
      <div
        v-for="album in selection"
        :key="album.name" 
  
        class="border border-black my-4 p-2 flex justify-between"
      >
        <h3 class="w-1/5">{{ album.artiste }}</h3>
        <span class="w-1/5">Date de sortie : {{ album.dateSortie }}</span>
        <span class="w-1/5">Genre : {{ album.genre }}</span>
        <img :src=album.photo alt="cover album" class="h-12">

        <delete-button class="w-1/5"
        >

        </delete-button>
      </div>
    </div>

  </div>
  
</template>

<script>
export default {
  name: "selection-list",
  props: ['selection'],
  methods: {

  }}
</script>

<style>
</style>