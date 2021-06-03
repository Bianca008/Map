<template>
<html>
  <head>
    <link rel="stylesheet" type="text/css" href="https://unpkg.com/leaflet/dist/leaflet.css" />
  </head>
  <body>

    <div id="app" style="height: 400px">
      <v-map :zoom=13 :center="[47.413220, -1.219482]">
        <v-tilelayer url="https://{s}.tile.openstreetmap.org/{z}/{x}/{y}.png"></v-tilelayer>
        <v-marker :lat-lng="[47.413220, -1.219482]"></v-marker>
      </v-map>
    </div>
  </body>
</html>
</template>

<script>
export default {
  name: 'MapComp',
  props: {
    msg: String
  }
}
</script>