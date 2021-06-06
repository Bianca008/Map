<template>
<div>
        <div class="column">
            <map-comp :dataToSend="dataTable"></map-comp>
        </div>
        <div class="column">
            <button @click="loadData">Load data</button>
            <component v-bind:is="currentComponent" :dataToSend="dataTable"/>
            <!-- <table-comp prop-name="dataTable" @click="loadData"></table-comp> -->
        </div>
</div>
</template>

<script>

import MapComp from './components/MapComp.vue'
import TableComp from './components/TableComp.vue'
import EmptyComp from './components/EmptyComp.vue'
import axios from 'axios'

export default {
  name: 'App',
  components: {
    MapComp,
    TableComp
  },
  data(){
    return {
      dataTable: [],
      currentComponent: EmptyComp
      //isVisible: false,
    }
  },
  methods:{
    loadData: function(){
      axios.get('./response.json').then((response)=>{this.dataTable = response.data; console.log(this.dataTable); return response.data;})
      this.currentComponent = TableComp
    }
  },
  props:{
    dataToSend: []
  }
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

.column{
   float:left;
   width: 50%;
}

button{
  margin-top: 9%;
  background-color: chartreuse;
}
</style>
