<template>
  <div id="app">
    <Header/>
      <Item label="fazer app de todo" v-bind:done="false"/>
    <Footer/>
  </div>
</template>

<script>
import Header from './components/Header.vue';
import Footer from './components/Footer.vue';
import Item from './components/Item.vue';

export default {
  name: 'App',
  components: {
    Header,
    Footer,
    Item,
  }
}
</script>

<style>
  body {
    margin: 0;
  }

  #app {
    font-family: Avenir, Helvetica, Arial, sans-serif;
    -webkit-font-smoothing: antialiased;
    -moz-osx-font-smoothing: grayscale;
  }
</style>
