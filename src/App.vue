<template>
  <div
    id="app"
    :style="backgroundGradient"
    @mousemove="redefinePositions"
    @mouseleave="resetPositions"
  >
    <img alt="Vue logo" src="./assets/logo.svg" />
    <HelloWorld msg="Katalid em Manutenção" />
  </div>
</template>

<script>
import { bgColorFrom, bgColorTo } from "./styles/variables.scss";
import HelloWorld from "./components/HelloWorld.vue";

export default {
  name: "App",
  components: {
    HelloWorld,
  },
  data() {
    return {
      gradientX: "50%",
      gradientY: "0%",
    };
  },
  computed: {
    backgroundGradient() {
      return {
        background: `radial-gradient(circle at ${this.gradientX} ${this.gradientY}, ${bgColorFrom}, ${bgColorTo})`,
      };
    },
  },
  methods: {
    redefinePositions({ clientX, clientY }) {
      this.gradientX = `${clientX}px`;
      this.gradientY = `${clientY}px`;
    },
    resetPositions() {
      this.gradientX = "50%";
      this.gradientY = "0";
    },
  },
};
</script>

<style lang="scss">
@import "./styles/reset.scss";
body {
  background-color: black;
}
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  display: flex;
  flex-direction: column;
  height: 100%;
  min-height: 100vh;

  img {
    width: 10vw;
    display: flex;
    flex-direction: column;
    margin: 25vh auto 2vh;
  }
}
</style>
