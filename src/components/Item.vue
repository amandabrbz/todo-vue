<template>
  <section>
    <div>
      <input
        type="checkbox"
        v-bind:for="id"
        v-bind:checked="isDone"
        @change="$emit('change')"
      />
      <label v-bind:for="id">{{ label }}</label>
    </div>
    <div>
      <button @click="$emit('delete')">x</button>
    </div>
  </section>
</template>

<script>
export default {
  name: "Item",
  props: {
    label: { required: true, type: String },
    done: { default: false, type: Boolean },
    id: { required: true, type: String },
  },
  data() {
    return {
      isDone: this.done,
    };
  },
  methods: {
    delete() {
      this.$emit("delete");
    },
  },
};
</script>

<style scoped>
section {
  display: flex;
  justify-content: space-between;
  align-items: center;
}

div {
  display: flex;
  justify-content: flex-start;
  align-items: center;
}

div > input[type="checkbox"] {
  width: 20px;
  height: 20px;
  cursor: pointer;
  margin-right: 20px;
}

div > label {
  color: #4f7947;
}

button {
  background: red;
  color: white;
  border: 1px solid red;
  width: 20px;
  height: 20px;
  font-weight:bold;
}
</style>
