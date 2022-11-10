<script>
// import HelloWorld from './components/HelloWorld.vue'
// import TheWelcome from './components/TheWelcome.vue'
// import TestEcharts from './components/TestEcharts.vue';
import EnterprisePicIco from './components/EnterprisePicIco.vue'
import EnterprisesPic from './components/EnterprisesPic.vue'
import SingleEnterprisePic from './components/SingleEnterprisePic.vue'
import MapNetwork from './components/MapNetwork.vue'

// import NetworkAndNodeImportance from './components/NetworkAndNodeImportance.vue'
import NetworkAndNodeImportance_newVue from './components/NetworkAndNodeImportance_new.vue'
import EnterpriseAsset from './components/EnterpriseAsset.vue'

import Network3D from './components/Network3D.vue'
import Network25D from './components/Network25D.vue'
import Search from './components/Search.vue'
// import * as echarts from 'echarts';

export default {
  data() {
    return {
      test: 0
    }
  },
  computed: {

  },
  methods: {

  },
  watch: {},
  components: {
    // TestEcharts: TestEcharts,
    EnterprisePicIco: EnterprisePicIco,
    EnterprisesPic:EnterprisesPic,
    SingleEnterprisePic:SingleEnterprisePic,
    MapNetwork:MapNetwork,
    NetworkAndNodeImportance_newVue:NetworkAndNodeImportance_newVue,
    EnterpriseAsset:EnterpriseAsset,
    Network3D:Network3D,
    Network25D:Network25D,
    Search:Search
    // TestEcharts
  }
}
</script>

<template>
  <div id="root">
    <div id="div_1">
      <div id="div_1_1"><EnterprisePicIco></EnterprisePicIco></div>
      <div id="div_1_2"><EnterprisesPic></EnterprisesPic></div>
      <div id="div_1_3"><SingleEnterprisePic></SingleEnterprisePic></div>
    </div>

    <div id="div_2">
      <div id="div_2_1"><MapNetwork></MapNetwork></div>
      <div id="div_2_2">
        <div id="div_2_2_1"><Network3D></Network3D></div>
        <div id="div_2_2_2"><Network25D></Network25D></div>
      </div>
    </div>

    <div id="div_3">
      <div id="div_3_1"><NetworkAndNodeImportance_newVue></NetworkAndNodeImportance_newVue></div>
      <div id="div_3_2"><EnterpriseAsset></EnterpriseAsset></div>
      <div id="div_3_3"><Search></Search></div>
    </div>
  </div>

</template>

<style>
#root{
  width: 100%;
  height: 100%;
}
#div_1 {
  border-color: lightsalmon;
  border-width: 1px;
  border-style: solid;
  /* border-left: 1px solid lightsalmon;
    border-right: 1px solid lightsalmon;
    border-bottom: 1px solid lightsalmon; */
  width: 25%;
  height: 100%;
  float: left;
}

#div_1_1 {
  /* border-color: lightsalmon;
    border-width: 1px;
    border-style: solid; */
  width: 100%;
  height: 15%;
  float: left;
  position: relative;
}

#div_1_2 {
  border-left: 1px solid lightsalmon;
  border-right: 1px solid lightsalmon;
  border-bottom: 1px solid lightsalmon;
  width: 100%;
  height: 51.7%;
  float: left;
  position: relative;
}

#div_1_3 {
  border-color: lightsalmon;
  border-width: 1px;
  border-style: solid;
  width: 100%;
  height: 33%;
  float: left;
  position: relative;
}

#div_2 {
  position: relative;
  border-color: lightsalmon;
  border-width: 1px;
  border-style: solid;
  width: 49.2%;
  height: 100%;
  float: left;
  position: relative;
}

#div_2_1 {
  border-color: lightsalmon;
  border-width: 1px;
  border-style: solid;
  width: 100%;
  height: 66.8%;
  float: left;
  position: relative;
}

#div_2_2 {
  border-color: lightsalmon;
  border-width: 1px;
  border-style: solid;
  width: 100%;
  height: 32.9%;
  float: left;
}
#div_2_2_1{
  border-color: lightsalmon;
  border-width: 1px;
  border-style: solid;
  width: 49.6%;
  height: 100%;
  float: left;
}
#div_2_2_2{
  border-color: lightsalmon;
  border-width: 1px;
  border-style: solid;
  width: 50%;
  height: 100%;
  float: left;
}

#div_3 {
  border-color: lightsalmon;
  border-width: 1px;
  border-style: solid;
  width: 25%;
  height: 100%;
  float: left;
}

#div_3_1 {
  border-color: lightsalmon;
  border-width: 1px;
  border-style: solid;
  width: 100%;
  height: 40%;
  float: left;
}

#div_3_2 {
  border-color: lightsalmon;
  border-width: 1px;
  border-style: solid;
  width: 100%;
  height: 26.6%;
  float: left;
}

#div_3_3 {
  border-color: lightsalmon;
  border-width: 1px;
  border-style: solid;
  width: 100%;
  height: 32.9%;
  float: left;
}
</style>
