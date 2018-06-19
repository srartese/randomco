<template>
  <div id="app">
   <component v-bind:is="component" v-bind:time-out="timeOut" v-on:updateBoolean="changeComponent($event)" > </component>
  <button v-on:click=" component='Form'; hide()" v-if="!enter"> Join the Conversation! </button>
  </div>
</template>

<script>
import Attract from './components/Attract'
import Form from './components/Form'

export default {
  name: 'App',
  components: {
    Attract,
    Form
  },
  data () {
    return{
      component: 'Attract',
      enter: false,
      timeOut: true
    }
  },
  methods:{
    // Hide elements when components change
    hide: function(){
      // Console.log("hide component");
      this.enter = true;
      this.timeOut = false;
    },
    // Change component based on the child's data emitted back to parent
    changeComponent: function(bool){
      this.timeOut = bool;
      this.enter = false;
      this.component = Attract;
    }
  }
}
</script>

<style>
#app {
  font-family: 'Avenir', Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  color: #2c3e50;
  margin-top: 60px;
}

button{
  z-index: 2;
  position: absolute;
  top: 50%;
  height: 10%;
  width: 15%;
  margin: 0 auto;
  font-size: 1em;
  border-radius: 5%;
  left: 43%;
}
</style>
