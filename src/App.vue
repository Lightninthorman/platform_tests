<template>
  <div id="app">
      <Testing :height="options.height" @new-height="updateHeight"/>
      <div id="tiles">
    <!-- <square text="This is a square" size="small"/>
    <square text="This is a square" size="medium"/>
    <square text="This is a square" size="large"/>
    <square text="This is a square" size="large" color="#000"/> -->
    <div class="g__tile_wrapper" >
      <Tiles
        v-for="data in records"
        :key="data.text"
        :height="height"
        :text="data.text"
        :href="data.href"
        :description="data.description"
        :size="data.size"
        :color="data.color"

      />
    </div>
  </div>
  </div>
</template>

<script>
import Testing from './components/Testing.vue';
import Tiles from './components/Tiles.vue';
import json from './json/data.json';

export default {
    name: "App",
    components: {Testing, Tiles},
    data(){
    return{
            records: json.records,
            options: json.options,
            height: json.options.height
        }
    },
    methods:{
        updateHeight(newHeight){
            console.log("called in app");
            this.height = newHeight;
        }
    }

};
</script>

<style >
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}
.g__tile_wrapper{
  display: flex;
  flex-wrap: wrap;
  justify-content: center;
  flex-direction: row;
  align-items: center;
}


</style>
