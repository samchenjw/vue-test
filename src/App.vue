<template>
  <!-- <img alt="Vue logo" src="./assets/logo.png" /> -->
  <HelloWorld  msg="Welcome to Your  App" />
  {{test}}

  <FooBar :message="'hi foo'" />
</template>

<script lang="ts">
import { Options, Vue } from "vue-class-component";
import HelloWorld from "./components/HelloWorld.vue";
import FooBar from './components/FooBar.vue';
@Options({
  components: {
    HelloWorld,
    FooBar,
  },
})
export default class App extends Vue {
  test: number = 3;

  created() {
    console.log(this.test);
  }
}
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
