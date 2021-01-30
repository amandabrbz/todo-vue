<template>
  <div>
    <input type="checkbox" v-bind:for="id" v-bind:checked="isDone" />
    <label v-bind:for="id">{{label}}</label>
  </div>
</template>

<script>
export default {
  name: "Item",
  props: {
    label: { required: true, type: String },
    done: { default: false, type: Boolean },
  },
  data() {
    return {
      isDone: this.done,
      id: `id-${Math.floor(Math.random() * 1000)}`,
    };
  }
};
</script>

<style scoped></style>
