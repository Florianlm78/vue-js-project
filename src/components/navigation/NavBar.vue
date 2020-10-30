<template>
<div class="bg-green-300">
    <a class="p-3" href="#" @click.prevent="changeComponent('album-view')">Tout les albums</a>
    <a href="#" @click.prevent="changeComponent('selection-list')">Ma selection</a>
</div>
</template>

<script>
export default {
  name : "nav-bar",

  methods:{
    changeComponent(value){
      this.$emit('change-component', value)
    }
  },


}
</script>

<style>

</style>