<template>
  <fieldset>
    <legend>Dados do veiculos</legend>
    <label for="placa">Placa:</label>
    <input type="text" id="placa" placeholder="informe a placa" maxlength="8" v-model="placa" />
    <button @click="pesquisarVeiculo">OK</button>
  </fieldset>
</template>

<script>
export default {
  data: function() {
    return {
      placa: ""
    };
  },
  methods: {
    pesquisarVeiculo: function() {     
      this.$store.state.infracoesVeiculo = this.$store.state.multas.filter(multa => multa.PLACA == this.placa);
      this.$router.push("/infracoes")
    }
  }
};
</script>