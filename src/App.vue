<template>
  <div id="app">
    <h1>Math Quiz App</h1>
    <OperatorQuiz @onBack="clearOperator" v-if="operator" :operator="operator"/>
    <OperatorSelector v-if="!operator" @changeOperator="changeOperator"/>
   
   
  </div>
  
</template>

<script>
import OperatorSelector from "./components/OperatorSelector.vue"  
import OperatorQuiz from "./components/OperatorQuiz.vue"
export default {
    name: "app",
    data() {
      return {
        operator: null,
      }
    },
    methods: {
      changeOperator(operator) {
        this.operator = operator
      },
      clearOperator() {
        this.operator = null;
      }
    },
    components: {
      OperatorSelector,
      OperatorQuiz,
    }
}
</script>

<style>
#app {
  font-family: "Avenir", Helvetica, Arial, sans-serif ;
  -webkit-font-smoothing: antialiased;
  -moz-osz-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}  
button {
  padding: 33px;
  margin: 5px;
  width: 175px;
  height: 95px;
  font-size: 22px;
  background-color: #10aeb2;
  color: white;
}
</style>