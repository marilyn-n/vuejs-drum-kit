<template>
  <div id="app">
    <DrumKit/>
  </div>
</template>

<script>
import DrumKit from './components/DrumKit';

export default {
  name: 'App',
  components: {
    DrumKit,
  },
};
</script>

<style>
#app {
  font-family: 'Avenir', Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
}
body {
  margin: 0;
}
</style>
