// App.vue
<template>
  <h1 class="text-center">Conversor de Moedas</h1>
  <div id="app">
    <div class="linha">
    <Conversor moeda-a="USD" moeda-b="BRL"/>
    <Conversor moeda-a="BRL" moeda-b="USD"/>
  </div>
  <div class="linha">
    <Conversor moeda-a="CAD" moeda-b="BRL"/>
    <Conversor moeda-a="BRL" moeda-b="CAD"/>
  </div>
  <div class="linha">
    <Conversor moeda-a="EUA" moeda-b="BRL"/>
    <Conversor moeda-a="BRL" moeda-b="EUA"/>
  </div>
  </div>
</template>

<script>
import Conversor from "./components/Conversor.vue"
export default {
  name: "app",
  components: {
    Conversor
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

.linha {
  margin-top: 40px;
  display: flex;
  justify-content: space-around;
}

.text-center {
  text-align: center;
}
</style>
