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
    id: {required: true, type: String}
  },
  data() {
    return {
      isDone: this.done,
    };
  }
};
</script>

<style scoped></style>
