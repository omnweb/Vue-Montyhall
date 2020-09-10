<template>
  <div id="app-2">
    <h1>Desafio de Montyhall</h1>  
    <div class="form">
      <div v-if="!started">
        <!-- Só vai aparecer aqui se não estiver estartado -->
        <label for="portsAmount">Selecione o número de portas:</label>
        <input type="text" id="portsAmount" size="3" 
          v-model.number="portsAmount">
      </div>
      <div v-if="!started">
        <!-- Só vai aparecer aqui se não estiver estartado -->
        <label for="selectedPort">Selecione o número da porta que contém o prêmio:</label>
        <input type="text" id="selectedPort" size="3" 
          v-model.number="selectedPort">
      </div>
      <button v-if="!started" @click="started= true" type="Button">Iniciar</button>
      <button v-if="started" @click="started= false" type="Button">Reiniciar</button>
    </div>
    <div class="doors" v-if="started">
      <div v-for="i in portsAmount" :key="i">
        <Door :hasGift="i == selectedPort" :number="i"/>
      </div>
    </div>
  </div>
</template>

<script>
import Door from './components/Door'
export default {
  name:'App', 
    components: {Door},
    data: function(){
      //Estes dados representam o estado do componente
      return{
        started: false,
        portsAmount: 3, 
        selectedPort: null
      }

    }
}
</script>

<style>
@font-face {
    font-family: "Oswald";
    src: url("./fonts/Oswald-Regular.ttf");
}
* {
    box-sizing: border-box;
    font-family: "Oswald-Regular.ttf", sans-serif;
}
body{
  color: white;
  background: linear-gradient(to right, #00bf8f, #001510); /* W3C, IE 10+/ Edge, Firefox 16+, Chrome 26+, Opera 12+, Safari 7+ */

}
#app-2{
  display: flex;
  flex-direction: column;  
  align-items: center;
}
#app-2 h1 {
  border: solid 1px #00bf8f;
  background-color: #001510a4;
  padding: 20px;
  margin-bottom: 60px;
}
.gift {
  position: relative;
  display: flex;
  flex-direction: column;
  align-items: center;
  z-index: 10;
}
.gift-top{
  width: 100px;
  height: 25px;
  background-color: #bb8e35;
}
.gift-body {
  width: 90px;
  height: 60px;
  background-color: #fabd45;
}
.gift-tie-1 {
  position: absolute;
  margin-top: 25px;
  width: 15px;
  height: 60px;
  background-color: red;
}
.gift-tie-2 { 
  position: absolute;
  margin-top: 45px;
  width: 90px;
  height: 15px;
  background-color: red;
}
.form {
  display: flex;
  flex-direction: column;
  justify-content: center;
  align-items: center;
  margin-bottom: 40px;
}
.form , .form input, .form button {
  margin-bottom: 10px;
  font-size: 2rem;
}
.doors{
  display: flex;
  align-self: stretch;
  justify-content: space-around;
  flex-wrap: wrap;
}
</style>