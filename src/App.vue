<template>
  <div id="app">
    <button v-show="!isVisible" @click="isVisible = !isVisible; tree=''">
      Back
    </button>
    <div v-show="isVisible">
      <Perk name="Int" :img-url="'https://image.shutterstock.com/image-vector/three-gear-sign-simple-icon-260nw-417078436.jpg'" max-value=20 />
    </div>
    <button @click="isVisible = !isVisible; tree='Breach'" v-show="isVisible">Breach</button>
    <div v-if="tree === 'Breach'">
      <PerksTree :name='tree' />
    </div>
    <button @click="isVisible = !isVisible; tree='Quickhacks'" v-show="isVisible">Quickhacks</button>
    <div v-if="tree === 'Quickhacks'">
      <PerksTree :name='tree' />
    </div>
  </div>
</template>

<script>
import PerksTree from './components/PerksTree.vue'
import Perk from './components/Perk.vue'

export default {
  name: 'App',
  components: {
    PerksTree,
    Perk,
  },
  data: function() {
    return {
      isVisible: true,
      tree: "",
    }
  },
}
</script>

<style>
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}
</style>
