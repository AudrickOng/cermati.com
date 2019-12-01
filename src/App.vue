<template>
  <div id="app">
    <transition name="fade">
      <div v-if="mounted" class="root">
        <Panel />
        <Header />
        <Body />
        <Footer />
        <News />
      </div>
    </transition>
  </div>
</template>

<script>
import Panel from "./components/Panel.vue";
import Header from "./components/Header.vue";
import Body from "./components/Body.vue";
import Footer from "./components/Footer.vue";
import News from "./components/News.vue";

require("vue2-animate/dist/vue2-animate.min.css");

export default {
  name: "app",
  components: {
    Panel,
    Header,
    Body,
    Footer,
    News
  },
  data() {
    return {
      mounted: false
    };
  },
  mounted() {
    this.mounted = true;
  }
};
</script>

<style>
@import url("https://fonts.googleapis.com/css?family=Roboto:300,400,500,700&display=swap");
#app {
  min-height: 100vh;
  max-width: 100vw;
  display: inline-grid;
}
.root {
  overflow-x: hidden;
  display: inline-grid;
}
</style>
