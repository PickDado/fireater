<template>

  <div style="height: 600px; wight:90%;">

     <!-- <div>{{dati}}</div> -->

    
    <l-map
      style="height: 80%; width: 100%"
      :zoom="zoom"
      :center="center"
      @update:zoom="zoomUpdated"
      @update:center="centerUpdated"
      @update:bounds="boundsUpdated"  
    >

    

    <l-marker

    v-for="da in dati"
    :key="da"
    :lat-lng="latLng(da.latitude,da.longitude)"
    ></l-marker>
    
      <l-tile-layer :url="url"></l-tile-layer>
    </l-map>
  </div>
</template>

<script>
import L from "leaflet"; 
import {LMap, LTileLayer, LMarker} from 'vue2-leaflet';

export default {
    name:"FireMap2",
  components: {
    LMap,
    LTileLayer,
    LMarker,
  },
  data () {
    return {
      url: 'https://{s}.tile.openstreetmap.org/{z}/{x}/{y}.png',
      zoom: 2,
      center: [26.303231, 50.160695],
      bounds: null,
        
          
       };
  },
  props:{
    dati:String
  },

   

  methods: {
    zoomUpdated (zoom) {
      this.zoom = zoom;
    },
    centerUpdated (center) {
      this.center = center;
    },
    boundsUpdated (bounds) {
      this.bounds = bounds;
    },
    latLng: function(lat, lng){
        return L.latLng(lat,lng);
    }
  },
  
}
</script>

<style scoped>
*{
  margin: 0;
  padding:0;
}
</style>