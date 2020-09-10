<template>
  <div class="door-area">
      <div class="door-frame" :class="{selected: selected && !open}">
          <!-- Caso as duas variáveis forem verdadeiras o presente some -->
          <Gift v-if="open && hasGift"/>
      </div>
      <div class="door" :class="{open}" @click="selected = !selected">
           <!-- Propriedade passada pelo componente  -->
           <div class="number" :class="{selected}" >{{number}}</div>
           <!-- Massaneta da porta -->
           <div class="knob" :class="{selected}" @click="open = true"></div>
      </div>
  </div>
</template>

<script>
import Gift from './Gift'
export default {
    name: 'Door',
    components: {Gift},
    props: {
        // Propriedades dos dados de entrada do componente
        number:{}, // Quantidade de portas
        hasGift: {type: Boolean}
    },
    data: function(){
        //Componente possui 4 estados que precisam ser verificados
        // Verificar se a porta está fechada, se a porta está aberta, se está selecionada e
        // saber se tem ou não o presente 
        return {
            //estado inicial, porta começa fechada e sem seleção
            open: false,
            selected: false
        }
    }
}
</script>

<style>
:root{
    --door-border: 5px solid #00bf8f;     
    --selected-boreder: 5px solid #fabd45;  
}
.door-area {
    position: relative;
    width: 200px;
    height: 310px;
    border-bottom: 10px solid #aaa;
    margin-bottom: 20px;
    font-size: 3rem;

    display: flex;
    justify-content: center;
}
.door-frame {
    position: absolute;
    height: 300px;
    width: 180px;

    border-left: var(--door-border);
    border-top: var(--door-border);
    border-right: var(--door-border);
    display: flex;
    justify-content: center;
    align-items: flex-end;
}

.door {
    position: absolute;
    top: 5px;
    height: 295px;
    width: 170px;
    background-color: #001510;

    display: flex;
    align-items: center;
    flex-direction: column;
    padding: 20px;
}

.door .knob {
    margin-top:60px;
    height: 20px;
    width: 20px;
    border-radius: 10px;
    background-color: #00bf8f;
    align-self: flex-start;
}
.door-frame.selected {
    border-left: var(--selected-boreder);
    border-top: var(--selected-boreder);
    border-right: var(--selected-boreder);
}
.door .number.selected {
    color:#fabd45;
}

.knob.selected {
    background-color: #fabd45;
}

.door.open {
    background-color: #0007;
}

.door.open .knob {
    display: none;
}
.door.open .number {
    display: none;
}
</style>