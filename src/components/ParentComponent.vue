<template>
  <div>
    ParentComponent
    <br />
    <input type="text" v-model="parentMsg" />
    <Child :message="parentMsg" @my-event="myEvent"></Child>
  </div>
</template>

<script>
import Child from "@/components/ChildComponent.vue";

export default {
  name: "ParentComponent",
  components: {
    Child,
  },
  data() {
    return {
      parentMsg: "pppppppppp",
    };
  },
  methods: {
    myEvent(event) {
      console.log(event);
    },
    parentLog(text) {
      console.log(text);
    },
  },
};
</script>

<style scoped>
</style>