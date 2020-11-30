<template>
  <div id="app">
    <Gatos/>
  </div>
</template>

<script>
import Gatos from './components/Gatos.vue'

export default {
  name: 'App',
  components: {
    Gatos
  }
}
</script>

<style>
#app {
  width: 100%;
  height: auto;
  margin: 0;
  padding: 0;
  border: 0;
  display: flex;
  align-content: center;
  justify-content: center;
  background: rgb(87, 84, 82);
  font-family: 'Lucida Sans', 'Lucida Sans Regular', 'Lucida Grande', 'Lucida Sans Unicode', Geneva, Verdana, sans-serif;
}
</style>
