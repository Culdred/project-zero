<template>
    <div>
        <button @mousedown.left="addValue()" @mousedown.right="subtractValue()" @contextmenu.prevent="">
            <img :src="imgUrl">
            {{ value }} / {{ maxValue }}
            <br>
            {{ name }}
        </button>
    </div>
</template>

<script>
export default {
    props: {
        name: String,
        maxValue: Number,
        imgUrl: String,
    },
    data: function() {
        return {
            value: 0,
        }
    },
    methods: {
        addValue() {
            if(this.value < this.maxValue) {
                return this.value++;
            }
        },
        subtractValue() {
            if(this.value > 0) {
                return this.value--;
            }
        }
    }
}
</script>

<style>
    img {
        height: 50px;
        width: 50px;
    }
</style>