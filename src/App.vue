<template>
  <div id="app-2">
    <h1>Desafio de Montyhall</h1>  
    <Door number="1" :hasGift="false" />  
  </div>
</template>

<script>
import Door from './components/Door'
export default {
  name:'App', 
    components: {Door}
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
  background-color: #36979c;
}
.gift-body {
  width: 90px;
  height: 60px;
  background-color: #40bbc1;
}
.gift-tie-1 {
  position: absolute;
  margin-top: 25px;
  width: 15px;
  height: 60px;
  background-color: #fabd45;
}
.gift-tie-2 { 
  position: absolute;
  margin-top: 45px;
  width: 90px;
  height: 15px;
  background-color: #fabd45;
}
</style>