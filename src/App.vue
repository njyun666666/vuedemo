<template>
  <!-- <img alt="Vue logo" src="./assets/logo.png" /> -->
  <HelloWorld msg="Welcome to Your Vue.js App" />
  <DemoComponent></DemoComponent>
  <buttonCount></buttonCount>
  <buttonCount></buttonCount>
  <ParentComponent></ParentComponent>

  <div>
    <ul class="nav">
      <li>
        <a href="#" @click.prevent="changeView('home')">home</a>
      </li>
      <li>
        <a href="#" @click.prevent="changeView('posts')">posts</a>
      </li>
    </ul>
    <keep-alive>
      <component :is="view"></component>
    </keep-alive>
  </div>
</template>

<script>
import ButtonCountVue from "./components/ButtonCount.vue";
import DemoComponentVue from "./components/DemoComponent.vue";
import HelloWorld from "./components/HelloWorld.vue";
import HomeComponentVue from "./components/HomeComponent.vue";
import ParentComponentVue from "./components/ParentComponent.vue";
import PostsComponentVue from "./components/PostsComponent.vue";

export default {
  name: "App",
  components: {
    HelloWorld,
    DemoComponent: DemoComponentVue,
    ButtonCount: ButtonCountVue,
    ParentComponent: ParentComponentVue,
    home: HomeComponentVue,
    posts: PostsComponentVue,
  },
  data() {
    return {
      view: "home",
    };
  },
  methods: {
    changeView: function (view) {
      console.log(view);
      this.view = view;
    },
    rootLog: function () {
      console.log("root log");
    },
  },
};
</script>

<style>
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}
</style>
