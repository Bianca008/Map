<template>
    <div>
        <table>
            <tr>
                <th>Id</th>
                <th>Latitude</th>
                <th>Longitude</th>
            </tr>
            <tr v-bind:dataToSend="dataToSend" v-for="data in dataToSend.features" :key="data.params">
                <td>{{data.properties.Id}}</td>
                <td>{{data.geometry.coordinates[1]}}</td>
                <td>{{data.geometry.coordinates[0]}}</td>
            </tr>
        </table>
    </div>
</template>

<script>
//import json from '../response.json'

      export default{
          data(){
              return{
                  //myJson: json
              }
          },
          props: {
              dataToSend: []
          }
      }
</script>

<style scoped>

table{
    width: 100%;
    background-color: aqua;
    margin-top: 10%;
}

td{
    text-align: center;
    background-color: aquamarine;
}

</style>