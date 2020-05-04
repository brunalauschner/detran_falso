<template>
  <fieldset id="caixa">
    <legend id="titulo">Dados do veículo</legend>
    <label  for="placa" id="plac">Placa:</label>
    <input type="text" id="placa" placeholder=" Escreva aqui" maxlength="8" v-model="placa" />
    <button id="butao" @click="pesquisarVeiculo">OK</button>
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

<style>
#titulo{
  width: 180px;
  height: 30px;
  text-align: center;
  font-family: 'Segoe UI', Tahoma, Geneva, Verdana, sans-serif;
  font-size: 20px;
  background-color: rgb(209, 198, 101);
}
#caixa{
   width: 40%;
   height: 55px;
   margin: 100px 0px 0px 375px;
   background-color: rgb(231, 224, 162);
   text-align: center;
   padding: 30px;
}
#plac{
   font-family: 'Segoe UI', Tahoma, Geneva, Verdana, sans-serif;
   margin: 0px 10px 0px 0px;
}
#butao{
   font-family: 'Segoe UI', Tahoma, Geneva, Verdana, sans-serif;
   margin: 0px 0px 0px 5px;
   background-color: rgb(209, 198, 101);
}
</style>