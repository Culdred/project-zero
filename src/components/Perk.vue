<template>
  <div>
    <button
      :id="type"
      @mousedown.left="addValue()"
      @mousedown.right="subtractValue()"
      @contextmenu.prevent=""
    >
      <img :src="imgUrl" />
      {{ localValue }} / {{ maxValue }}
      <br />
      {{ name }}
    </button>
  </div>
</template>

<script>
export default {
  props: {
    name: String,
    type: String,
    maxValue: Number,
    imgUrl: String,
    value: Number,
  },
  data: function() {
    return {
      localValue: this.value,
    };
  },
  methods: {
    addValue() {
      if (this.localValue < this.maxValue) {
        this.localValue++;
        this.$emit("changeValue", this.localValue);
      }
    },
    subtractValue() {
      if (this.localValue > 0) {
        this.localValue--;
        this.$emit("changeValue", this.localValue);
      }
    },
  },
};
</script>

<style></style>
