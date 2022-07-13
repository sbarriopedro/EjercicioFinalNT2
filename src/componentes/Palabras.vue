<template>

  <section class="src-componentes-notas">
      <div class="jumbotron">
      <h2><i>Ingreso de Alumnos</i></h2>
      <hr>
      <br>
      <input type="text" placeholder="Color" @input="cambiarColor">
      <input type="text" placeholder="Fondo" @input="cambiarFondo">
      <input type="text" placeholder="Size" @input="cambiarTamanio">
      <br>
      <hr>
      <input type="text" v-model="input" :style="{color: color, 'font-size': size , backgroundColor: bgColor}">
      <div>{{size}}</div>
      <div>cantidad de palabras: {{ contadorDePalabras }}</div>
    </div>
  </section>

</template>

<script lang="js">

  export default  {
    name: 'src-componentes-palabras',
    props: [],
    mounted () {

    },
    data () {
      return {
        color: "",
        size: '17px',
        bgColor: "",
        input: ""
      }
    },
    methods: {
      cambiarTamanio: function(event) {
        console.log(event.target.value)
        this.size = event.target.value + 'px';
      },
      cambiarFondo: function(event) {
        this.bgColor = event.target.value;
      },
      cambiarColor: function(event) {
        this.color = event.target.value;
      }
    },
    computed: {
      contadorDePalabras() {
        return this.input.split(' ').length
        },
    }
}


</script>

<style scoped lang="css">
  .src-componentes-notas {

  }

  .jumbotron {
    background-color: #f4f4f4;
    color: rgb(133, 12, 12);
    border: 2px inset rgb(0,0,0,0.5);
  }

  hr {
    background-color: #999;
  }

  label {
    font-weight: bold;
  }
</style>
