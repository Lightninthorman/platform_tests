<template>
  <div id="Testing">
      <label>Height</label>
      <input v-model.number="componentHeight" @input="changeHeight" type="range" min="10" max="400"  class="slider">
  </div>
</template>

<script>


export default {
    name: "Testing",
    emits:["new-height"],
    props: {
        height: {
            type: Number,
            default: 400
        }
    },
    data(){
        return{
            componentHeight: this.height,
            // width:50
        }
    },
    methods:{
        changeHeight(){
            this.$emit('new-height', this.componentHeight)
        }
    }
};
</script>

<style>

#changeMe {
    width: 50%;
    height: 150px;
    border: 1px solid black;
    border-radius: 7px;
}
</style>
