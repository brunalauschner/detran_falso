<template>
  <div class="infracoes">

      <div id="caixaTotal" v-for="(infracao, index) in infracoes" :key="index">

        <label class="letras" for="placa">Placa: </label>
        <input type="text" id="placaq" :value="infracao.PLACA" /><br>
        
        <label class="letras" for="placa">Local: </label>
        <input type="text" id="localq" :value="infracao.LOCALIDADE" /><br>

        <h3 id="tit">Dados da Infração:</h3>

        <label class="letras" for="data">Tipo:</label>
        <input type="text" id="tipoq" :value="infracao.DADOS_INFRACAO.TIPO" /><br>
        
        <label class="letras" for="placa">Data e Hora:</label>
        <input type="text" id="datahoraq" :value="infracao.DADOS_INFRACAO.DATAHORA" /><br>
        
        <label class="letras" for="placa" id="infracaoq" v-if="infracao.DADOS_INFRACAO.TIPO == 'VELOCIDADE'">Velocidade Máxima: {{infracao.DADOS_INFRACAO.VEL_MAXIMA}} Km/h</label><br>

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
    background-color: rgb(231, 224, 162);
    text-align: center;
    width: 45%;
    height: 250px;
    margin: 100px 0px 0px 370px;
    padding: 30px 0px 0px 0px;
}
.letras{
  font-family: 'Segoe UI', Tahoma, Geneva, Verdana, sans-serif;
  font-size: 15px;
  margin: 0px 10px 0px 0px;
}
#tit{
  font-family: 'Segoe UI', Tahoma, Geneva, Verdana, sans-serif;
}
#botaoq{
  font-family: 'Segoe UI', Tahoma, Geneva, Verdana, sans-serif;
   margin: 20px 0px 0px 0px;
   width: 120px;
   height: 30px;
   background-color: rgb(209, 198, 101);
}
</style>



