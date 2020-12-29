<template>
  <div>
    <button
      :class="type"
      @mousedown.left="addValue"
      @mousedown.right="subtractValue"
      @contextmenu.prevent=""
    >
      <img :src="imgUrl" />
      {{ value }} / {{ maxValue }}
      <br />
      {{ name }}
    </button>
  </div>
</template>

<script>
export default {
  props: {
    name: {
      type: String,
      default: "",
    },
    type: {
      type: String,
      deafult: "",
    },
    maxValue: {
      type: Number,
      default: 0,
    },
    imgUrl: {
      type: String,
      default: "",
    },
    value: {
      type: Number,
      default: 0,
    },
  },
  methods: {
    addValue() {
      if (this.value < this.maxValue) {
        this.$emit("input", this.value + 1);
      }
    },
    subtractValue() {
      if (this.value > 0) {
        this.$emit("input", this.value - 1);
      }
    },
  },
};
</script>

<style></style>
