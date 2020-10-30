<template>
  
  <div class="border m-2 p-2 text-center w-1/6">

<div>
    <img :src=album.photo>
    <h1 class="font-bold">{{album.name}}</h1>
    <h2>{{album.artiste}}</h2>
    <h2>{{album.prix}}€</h2>
</div>

    <base-button class="px-3 rounded"
    @click="addToSelection"
    >
    </base-button>

  </div>
</template>

<script>

import BaseButton from './global/BaseButton'

export default {
    name: "album-card",
    props: ['album'],
    components:{
      BaseButton
    },

    computed: {

    },
    methods:{
        addToSelection(){
        this.$emit('add-album', this.album)
    }
    }
}
</script>

<style>

</style>