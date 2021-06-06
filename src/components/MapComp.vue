<template>
  <html>
    <head>
      <link
        rel="stylesheet"
        type="text/css"
        href="https://unpkg.com/leaflet/dist/leaflet.css"
      />
    </head>
    <body>
      <div id="app" style="height: 400px">
        <v-map :zoom="8" :center="[45.6, 25.3]">
          <v-tilelayer
            url="https://{s}.tile.openstreetmap.org/{z}/{x}/{y}.png"
          ></v-tilelayer>
          <div v-bind:dataToSend="dataToSend">
            <div v-if="dataToSend">
              <div v-for="data in dataToSend.features" :key="data.params">
                <v-marker
                  :lat-lng="[data.geometry.coordinates[1], data.geometry.coordinates[0]]"
                ></v-marker>
              </div>
            </div>
          </div>
          <!-- <v-marker :lat-lng="[47.413220, -1.219482]"></v-marker> -->
        </v-map>
      </div>
    </body>
  </html>
</template>

<script>
export default {
  name: "MapComp",
  props: {
    msg: String,
    dataToSend: [],
  },
};
</script>
