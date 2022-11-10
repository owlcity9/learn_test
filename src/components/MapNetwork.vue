<template>
  <div id="mapnetwork">
    <div id="div2_2_1"></div>
  </div>
</template>
<script>
import { Scene, LineLayer } from '@antv/l7';
import { GaodeMap } from '@antv/l7-maps';

export default {
  data() {
    return {

    }
  },
  mounted(){
    this.draw_map_network()
  },
  computed: {

  },
  methods: {
    draw_map_network() {
      const scene = new Scene({
        id: 'div2_2_1',
        map: new GaodeMap({
          pitch: 30,
          style: 'light',
          center: [121.50398, 31.21683],
          zoom:8,
          // rotation: 42.3999
        }),
        logoVisible: false //标识符不可见
      });
      scene.on('loaded', () => {
        fetch('/json/map_connect_data.json')
          .then(res => res.json())
          .then(data => {
            const layer = new LineLayer({})
              .source(data, {
                parser: {
                  type: 'json',
                  x: 'from_lon',
                  y: 'from_lat',
                  x1: 'to_lon',
                  y1: 'to_lat'
                }
              })
              .size(3.5)
              .shape('arc3d')
              .color('#60C1C4')
              .style({
                segmentNumber: 15,
                opacity: 0.8
              });
            scene.addLayer(layer);
          });
      });
    }
  },
  watch: {},
  components: {
  }
}
</script>
<style>
#mapnetwork {
  width: 100%;
  height: 100%;
}
#div2_2_1{
  width: 100%;
  height: 100%;
}
</style>