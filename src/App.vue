<template>
  <div id="app">
    <Header />
    <Form @add="addTask" />
    <ul>
      <li v-for="item in tasks" v-bind:key="item.id">
        <Item
          v-bind:label="item.label"
          v-bind:done="item.done"
          v-bind:id="item.id"
        />
      </li>
    </ul>
    <Footer />
  </div>
</template>

<script>
import Header from "./components/Header.vue";
import Footer from "./components/Footer.vue";
import Item from "./components/Item.vue";
import Form from "./components/Form.vue";

export default {
  name: "App",
  components: {
    Header,
    Footer,
    Item,
    Form,
  },
  data() {
    return {
      tasks: [],
    };
  },
  methods: {
    addTask(task) {
      this.tasks.push({
        id: `id-${Math.floor(Math.random() * 1000)}`,
        label: task,
        done: false,
      });
    },
  },
};
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

ul,
li {
  padding: 0;
  margin: 0;
  list-style: none;
}
</style>
