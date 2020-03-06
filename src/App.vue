<template>
  <div id="app">
    <h1 class="title-align">Conversor de moedas</h1>
    <div class="line">
      <converter currency-a="USD" currency-b="BRL" />
      <converter currency-a="BRL" currency-b="USD" />
    </div>
    <div class="line">
      <converter currency-a="CAD" currency-b="BRL" />
      <converter currency-a="BRL" currency-b="CAD" />
    </div>
    <div class="line">
      <converter currency-a="EUR" currency-b="BRL" />
      <converter currency-a="BRL" currency-b="EUR" />
    </div>
  </div>
</template>

<script>
import Converter from "./components/Converter.vue"
export default {
  name: 'App',
  components: {
    Converter
  }
}
</script>

<style>
#app {
  margin: auto;
  max-width: 900px;
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  color: #2c3e50;
  margin-top: 60px;
}
.line{
  margin-top: 40px;
  display: flex;
  justify-content: space-around;
}
.title-align{
  text-align: center;
}
</style>
