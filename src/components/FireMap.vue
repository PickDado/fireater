


<script>
import L from "leaflet"; 
import {LMap, LTileLayer, LMarker} from 'vue2-leaflet';

export default {
    name:"FireMap",
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
  props:["dati"],

   

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