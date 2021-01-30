<template>
  <div id="app">
    <Header />
    <Form @add="addTask" />
    
    <ul aria-labelledby="list-summary">
      <li v-for="item in tasks" v-bind:key="item.id">
        <Item
          v-bind:label="item.label"
          v-bind:done="item.done"
          v-bind:id="item.id"
          @change="updateTask(item.id)"
          @delete="deleteTask(item.id)"
        />
      </li>
    </ul>

    <h6 id="list-summary">{{ listSummary }}</h6>

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
    updateTask(id) {
      const updateTask = this.tasks.find((item) => item.id === id);
      updateTask.done = !updateTask.done;
    },
    deleteTask(id) {
      const itemIndex = this.tasks.findIndex(item => item.id === id);
      this.tasks.splice(itemIndex, 1);
    }
  },
  computed: {
    listSummary() {
      const numberFinishedItems = this.tasks ? this.tasks.filter((item) => item.done).length : null;
      return `${numberFinishedItems} de ${this.tasks.length} tarefas feitas`;
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

ul {
  max-width: 300px;
  margin: 0 auto;
}

h6 {
  text-align: center;
  color: #44BFE4;
}
</style>
