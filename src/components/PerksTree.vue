<template>
  <div id="app">
    {{ name }}
    <Perk name="Perk1" :img-url="'https://image.shutterstock.com/image-vector/three-gear-sign-simple-icon-260nw-417078436.jpg'" max-value=2 />
  </div>
</template>

<script>
import Perk from './Perk.vue'

export default {
  name: 'App',
  components: {
    Perk
  },
  props: {
      name: String,
  }
}
</script>