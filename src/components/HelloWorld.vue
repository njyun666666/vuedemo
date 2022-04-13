<template>
  <div class="hello">
    <h1>{{ msg }}</h1>
    <h1>{{ reveredMessage }}</h1>
    <h1 v-bind:title="msg1">{{ msg1 }}</h1>
    <input type="text" v-model="msg1" />
    <button class="title" v-on:click="changeShowStatus($event)">
      click me
    </button>

    <div v-if="isShow">ture</div>
    <div v-else>false</div>

    <div>
      <li v-for="(item, index) in items" :key="index">
        name:{{ item.name }}, age:{{ item.age }}
      </li>
    </div>
  </div>

  <br /><br />

  <div>
    <input type="text" v-model="firstName" />
    <input type="text" v-model="lastName" />
    <br />
    {{ fullName }}
    <br />
    {{ getFullName }}
  </div>

  <br />
</template>

<script>
export default {
  name: "HelloWorld",
  props: {
    msg: String,
  },
  data() {
    return {
      msg1: "qqqqqqqqqqqq",
      isShow: false,
      items: [
        { name: "a", age: 1 },
        { name: "b", age: 22 },
        { name: "c", age: 333 },
      ],
      firstName: "Foo",
      lastName: "Bar",
      fullName: "Foo Bar",
      count: 0,
    };
  },
  methods: {
    changeShowStatus: function (event) {
      console.log(event);
      this.isShow = !this.isShow;
    },
  },
  computed: {
    reveredMessage: function () {
      return this.msg.split("").reverse().join("");
    },
    getFullName: function () {
      return `${this.firstName} ${this.lastName}`;
    },
  },
  watch: {
    firstName: function (val) {
      this.fullName = val + " " + this.lastName;
    },
    lastName: function (val) {
      this.fullName = this.firstName + " " + val;
    },
  },
};
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
h3 {
  margin: 40px 0 0;
}
ul {
  list-style-type: none;
  padding: 0;
}
li {
  display: inline-block;
  margin: 0 10px;
}
a {
  color: #42b983;
}

.title {
  color: red;
}
</style>
