<template>
<div>
        <div class="column">
            <map-comp></map-comp>
        </div>
        <div class="column">
            <table-comp></table-comp>
        </div>
</div>
</template>

<script>

import MapComp from './components/MapComp.vue'
import TableComp from './components/TableComp.vue'

export default {
  name: 'App',
  components: {
    MapComp,
    TableComp
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
</style>
