<template>
  <div id="app">
    {{ name }}
    <div v-for="(perk, idx) in perks" :key="idx">
      <Perk
        :name="perk.name"
        :img-url="perk.imgUrl"
        :max-value="perk.maxValue"
      />
    </div>
  </div>
</template>

<script>
import Perk from "./Perk.vue";

export default {
  name: "App",
  components: {
    Perk,
  },
  props: {
    name: String,
    perks: Array,
  },
};
</script>
