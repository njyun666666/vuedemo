<template>
  <div>Message: {{ message }}</div>
  <div>
    <button @click="btnClick()">click</button>
    <br />
    <button @click="$root.rootLog()">rootLog</button>
    <br />
    <button @click="$parent.parentLog('1111111')">parent function</button>
  </div>
</template>

<script>
export default {
  name: "ChildComponent",
  props: {
    message: {
      type: String,
      default: "from child",
    },
  },
  methods: {
    btnClick() {
      this.$emit("my-event", "123");
    },
  },
};
</script>

<style scoped>
</style>