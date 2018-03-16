<template>
  <div id="app">
    <img src="./assets/logo.png">
    <!--<router-view/>-->
    <!--<Events></Events>-->
    <!--<Formdata></Formdata>-->
    <!--<Styles></Styles>-->
    <Parent></Parent>
  </div>
</template>

<script>
import HelloWorld from './components/HelloWorld'
import Events from './components/Event'
import Formdata from './components/formdata'
import Styles from './components/style'
import Parent from './components/sonparent/parent'
import Child from './components/sonparent/child'

export default {
  name: 'App',
  components:{         //绑定
    HelloWorld,
    Events,
    Formdata,
    Styles,
    Parent,
    Child
  }
}
</script>

<style>
#app {
  font-family: 'Avenir', Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}
</style>
