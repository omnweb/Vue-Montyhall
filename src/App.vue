<template>
  <div id="app-2">
    <h1>Desafio de Montyhall</h1>    
  </div>
</template>

<script>
export default {

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
</style>