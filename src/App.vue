<template>
  <div id="app">
    <h1>Danny Francisco Hernandez Godoy - MercadoLibre</h1>
    <Busqueda v-on:formSubmit="mercadobuscar">    </Busqueda>
    <Lista :object='info'/>
    
  </div>
</template>

<script>
import Busqueda from "./components/Busqueda.vue";
import Lista from "./components/Lista.vue";

export default {
  name: "app",
  components: {
    Busqueda,
    Lista,
  },
  data: function() {
    return {
      listademercado: "",
      usuarioid: "",
      producto: [],
      precio: [],
      vendedorid: [],
      nombrev: [],
      info: []
    };
  },
  
  methods: {
    mercadobuscar: async function(texto) {
      //var caos
      this.$http
        .get(`https://api.mercadolibre.com/sites/MLC/search?q=${texto}`)
        .then(res => {
            //this.listademercado = res.body['results'];
            //this.info =this.listademercado
            this.info= res.data.results
            //console.log(this.info)
          //for(var i=0; i<this.listademercado.length; i++){
            //this.producto[i]=this.listademercado[i].title
            //this.precio[i]=this.listademercado[i].price
            //this.vendedorid[i]=this.listademercado[i].seller.id
            //this.nombrev[i]=this.nombrevendedor(this.vendedorid[i])
            //console.log(this.listademercado[i].price)
            //caos = this.listademercado[i].seller.id
            //console.log(caos)
            //this.nombrevendedor(318876164)
          //}
          //console.log(this.producto)
          //console.log(this.vendedorid)
          //console.log(this.nombrev)
        });
    },
    nombrevendedor: function(identificacion){
      this.$http
      .get(`https://api.mercadolibre.com/users/${identificacion}`)
      .then(resp => {
        this.usuarioid=resp.body['nickname'];
        //console.log(this.usuarioid)
      })
    }
  }
};
</script>

<style>
#app {
  font-family: "Avenir", Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}
</style>
