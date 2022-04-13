<template>
  <div>
    <button @click="count++">You clicked me {{ count }} times.</button>
  </div>
</template>

<script>
export default {
  name: "buttonCount",
  data() {
    return {
      count: 0,
    };
  },
};
</script>

<style>
</style>