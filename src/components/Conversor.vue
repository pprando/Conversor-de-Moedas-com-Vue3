// Conversor.vue
<template>
  <div class="conversor">
    <h2>{{ moedaA }} Para {{ moedaB }}</h2>
    <input type="text" v-model="moedaA_value" v-bind:placeholder="moedaA">
    <input type="button" value="Converter" v-on:click="converter">
    <h2>{{ moedaB_value }}</h2>
  </div>
</template>

<script>
export default {
  name: 'Conversor',
  props: ["moedaA", "moedaB"],
  data() {
    return {
      moedaA_value: "4",
      moedaB_value: "0"
    }
  },
  methods: {
    converter() {
      let de_para = this.moedaA + "-" + this.moedaB;
      let url = `https://economia.awesomeapi.com.br/last/${de_para}`;

      fetch(url)
        .then(res => res.json())
        .then(json => {
          let cotacao = json[de_para.replace('-', '')].ask;
          this.moedaB_value = (cotacao * parseFloat(this.moedaA_value)).toFixed(2);
        })
        .catch(error => {
          console.error('Erro ao buscar cotação:', error);
        });
    }
  }
}
</script>

<style scoped>
.conversor {
    padding: 20px;
    max-width: 300px;
    box-shadow: 0 4px 8px 0 rgba(0, 0, 0, 0.2);
}

</style>
