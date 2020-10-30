<template>

<nav-bar
  @change-component="changeSelectedComponent"
>
</nav-bar>

<keep-alive>
  <component 

    :is="selectedComponent"
    v-bind="currentProps"
    @child-event="selectionUpdate"
    >
  </component>
</keep-alive>






</template>

<script>

//import AlbumCard from './components/AlbumCard.vue'
import AlbumView from './components/AlbumView.vue'
import SelectionList from './components/SelectionList.vue'
import NavBar from './components/navigation/NavBar.vue'


export default {
  name: 'App',
  components: {
    //AlbumCard
    AlbumView,
    NavBar,
    SelectionList


  },

  data(){
    return{
        selectedComponent : 'album-view',
        albumSelection: []
    }
  },

  computed:{
    currentProps(){
      if(this.selectedComponent == "selection-list"){
      return {selection: this.albumSelection}
    }
    return false
    }
  },
  methods:{
    changeSelectedComponent(value){
      this.selectedComponent = value
    },
    selectionUpdate(value) {
      this.albumSelection.push(value)
    }

  }
}
</script>

<style>

</style>
