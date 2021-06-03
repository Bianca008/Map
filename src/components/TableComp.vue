<template>
    <div>
        <div v-for="data in myJson " :key="data.name">{{data}}</div>
        <!-- <template>
        <v-data-table : items="{myJson}">
        </v-data-table>
        </template> -->
        <!-- <vue-table-dynamic :params="myJson" ref="table"></vue-table-dynamic> -->
        <!-- <table>
            <thead>
                <tr>
                    <th>Name</th>
                    <th>Latitude</th>
                    <th>Long</th>
                </tr>
            </thead>
            <tbody>
                <tr v-for="data in myJson " :key="data.name">
                    <td>{{data.name}}</td>
                    <td>{{data.geometry.coordinates[0]}}</td>
                    <td>Long</td>
                </tr>
            </tbody>
        </table> -->
    </div>
</template>

<script>
      import json from '../response.json'
      export default{
          data(){
              return{
                  myJson: json
              }
          }
      }
</script>