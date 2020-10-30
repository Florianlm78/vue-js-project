<template>

<div class="list-none">
<selection-box
:selection="selection"
>
    
</selection-box>
</div>


<div class="flex justify-between flex-wrap">
  <album-card
  v-for="album in album.albums"
  :key="album.name"
  :album="album"
  @add-album="addAlbumToSelection"
  >

  </album-card>
</div>
</template>

<script>

import albumData from '../data/album.json'
import AlbumCard from './AlbumCard.vue'
import SelectionBox from './SelectionBox.vue'

export default {
    name: "album-view",
    components: {
        AlbumCard,
        SelectionBox
    },

    data(){
        return{
            album: albumData,
            selection: []
        }
    },

    methods:{
        addAlbumToSelection(album){
            this.selection.push(album)
            this.$emit('child-event', album)
        },

    }

}
</script>

<style>

</style>