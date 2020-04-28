<template>
  <div class="infracoes">

      <div id="caixaTotal" v-for="(infracao, index) in infracoes" :key="index">

        <label for="placa">Placa: </label>
        <input type="text" id="placaq" :value="infracao.PLACA" /><br>
        
        <label for="placa">Local: </label>
        <input type="text" id="localq" :value="infracao.LOCALIDADE" /><br>

        <h3>Dados da Infração:</h3>

        <label for="data">Tipo:</label>
        <input type="text" id="tipoq" :value="infracao.DADOS_INFRACAO.TIPO" /><br>
        
        <label for="placa">Data e Hora:</label>
        <input type="text" id="datahoraq" :value="infracao.DADOS_INFRACAO.DATAHORA" /><br>
        
        <label for="placa" id="infracaoq" v-if="infracao.DADOS_INFRACAO.TIPO == 'VELOCIDADE'">Velocidade Máxima: {{infracao.DADOS_INFRACAO.VEL_MAXIMA}} Km/h</label><br>

        <button id="botaoq" @click="voltar"> Nova Consulta </button>
      </div>

  </div>
</template>

<script>
export default {
  computed: {
    infracoes: function() {
        return this.$store.state.infracoesVeiculo
    },
    methods: {
        voltar: function(){
            this.$router.push('/')
        }
    }
    
    
  }
};

//mounted(){
    //    if(this.$store.state.infracoesVeiculo.lenght == 0){
    //        this.$router.push("/")
    //    }
    //}
</script>

<style>

#caixaTotal{
    border: 1px solid;
    
}

</style>



