<template>
  <div id="app">
    <img alt="Vue logo" src="./assets/logo.png">
    <MiComponente msg="Componente PARA Reuso" :posts="posts"/>
    <h1>Componente CON Reuso</h1>
    <div class="divisor-graficas">
      <h2 style="color:white">Ventas</h2>
      <VueFunnelGraph :width="width" :height="height" :labels="labels"
                    :values="values" :colors="colors" :sub-labels="subLabels" :direction="direction"
                    :gradient-direction="gradientDirection"
                    :animated="true" :display-percentage="true"
      ></VueFunnelGraph>
    </div>
  </div>
</template>

<script>
// import HelloWorld from './components/HelloWorld.vue'
import MiComponente from './components/MiComponente.vue'
import {VueFunnelGraph} from 'vue-funnel-graph-js'
// <HelloWorld msg="Welcome to Your Vue.js App"/>

export default {
  name: 'app',
  components: {
    // HelloWorld,
    MiComponente,
    VueFunnelGraph
  },

  data () {
    return {
      posts: {
        1:{
          title: "Producto 1",
          content: "Ingresa una descripción del producto 1",
          link: "/",
          linkLabel:"Comprar $1.00",
          image:'https://encrypted-tbn0.gstatic.com/images?q=tbn%3AANd9GcSbmCfLriVQzn0B8Cgrc8fjsBdmYsl3R68FMrSdH8VG6vCwr7kS',
        },
        2:{
          title: "Producto 2",
          content: "Ingresa una descripción del producto 2",
          link: "/",
          linkLabel:"Comprar $2.00",
          image:'https://encrypted-tbn0.gstatic.com/images?q=tbn%3AANd9GcSbmCfLriVQzn0B8Cgrc8fjsBdmYsl3R68FMrSdH8VG6vCwr7kS',
        },
        3:{
          title: "Producto 3",
          content: "Ingresa una descripción del producto 3",
          link: "/",
          linkLabel:"Comprar $3.00",
          image:'https://encrypted-tbn0.gstatic.com/images?q=tbn%3AANd9GcSbmCfLriVQzn0B8Cgrc8fjsBdmYsl3R68FMrSdH8VG6vCwr7kS',
        },
        4:{
          title: "Producto 4",
          content: "Ingresa una descripción del producto 4",
          link: "/",
          linkLabel:"Comprar $4.00",
          image:'https://encrypted-tbn0.gstatic.com/images?q=tbn%3AANd9GcSbmCfLriVQzn0B8Cgrc8fjsBdmYsl3R68FMrSdH8VG6vCwr7kS',
        },
        5:{
          title: "Producto 5",
          content: "Ingresa una descripción del producto 5",
          link: "/",
          linkLabel:"Comprar $5.00",
          image:'https://encrypted-tbn0.gstatic.com/images?q=tbn%3AANd9GcSbmCfLriVQzn0B8Cgrc8fjsBdmYsl3R68FMrSdH8VG6vCwr7kS',
        },
        6:{
          title: "Producto 6",
          content: "Ingresa una descripción del producto 6",
          link: "/",
          linkLabel:"Comprar $6.00",
          image:'https://encrypted-tbn0.gstatic.com/images?q=tbn%3AANd9GcSbmCfLriVQzn0B8Cgrc8fjsBdmYsl3R68FMrSdH8VG6vCwr7kS',
        },
      },
      labels: ['Impressions', 'Add To Cart', 'Buy'],
      subLabels: ['Direct', 'Social Media', 'Ads'],
          values: [
          // with the given Labels and SubLabels here's what the values represent:
          // 
          // Direct, Social, Ads  
          //    |      |     |  
          //    v      v     v
              [3000, 2500, 6500], // Segments of "Impressions" from top to bottom
              [3000, 1700, 1000], // Segments of "Add To Cart"
              [600,  200,  130]   // Segments of "Buy"
          ],
          colors: [
              ['#FFB178', '#FF3C8E'], // color set for "Impressions" segment
              ['#A0BBFF', '#EC77FF'], // color set for "Add To Cart" segment
              ['#A0F9FF', '#7795FF']  // color set for "Buy" segment
          ],
          direction: 'horizontal',
          gradientDirection: 'horizontal',
          height: 300,
          width: 800,
    }
  }
}
</script>

<style>
.divisor-graficas{
  margin-bottom: 60px;
  padding: 32px;
  background-color: #393862;
}
#app {
  font-family: 'Avenir', Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  /*color: #2c3e50;*/
  margin-top: 60px;
}
</style>
