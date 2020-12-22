<template>
  <div id="app">
    <button v-show="!isVisible" @click="isVisible = !isVisible; tree=''">
      Back
    </button>
    <div v-show="isVisible">
      <Stat name="Int" :img-url="'https://image.shutterstock.com/image-vector/three-gear-sign-simple-icon-260nw-417078436.jpg'" max-value=20 />
    </div>
    <button @click="isVisible = !isVisible; tree='Breach'" v-show="isVisible">Breach</button>
    <div v-if="tree === 'Breach'">
      <Perk name="Perk1" :img-url="'https://image.shutterstock.com/image-vector/three-gear-sign-simple-icon-260nw-417078436.jpg'" max-value=2 />
    </div>
    <br>
    <button @click="isVisible = !isVisible" v-show="isVisible">Quickhacks</button>
  </div>
</template>

<script>
import Stat from './components/Stat.vue'
import Perk from './components/Perk.vue'

export default {
  name: 'App',
  components: {
    Stat,
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
