<template>
  <div id="app">
    <div>
      <strong>{{ name }}</strong>
      <div v-for="(perk, idx) in perks" :key="idx">
        <Perk
          :name="perk.name"
          :type="'perk'"
          :img-url="perk.imgUrl"
          :max-value="perk.maxValue"
        />
      </div>
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
