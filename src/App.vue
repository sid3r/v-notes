<template>
  <div id="app">
    <!-- navbar -->
    <navbar />
    <!-- router view -->
    <div class="page-wrapper">
      <router-view />
    </div>
  </div>
</template>

<script>
import Navbar from "@/components/Navbar";

export default {
  components: { Navbar },
  created() {
    if (this.$workbox) {
      this.$workbox.addEventListener("waiting", () => {
        this.showUpgradeUI = true;
      });
    }
  },
  methods: {
    async accept() {
      this.showUpgradeUI = false;
      await this.$workbox.messageSW({ type: "SKIP_WAITING" });
    }
  }
};
</script>

<style lang="scss">
@import "styles/variables";
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  height: 100vh;
  overflow: hidden;
  background: $background;
  color: #5d5f62;

  display: flex;
  flex-direction: column;

  .page-wrapper {
    height: calc(100vh - 60px);
    flex: 1;
    overflow: hidden;
  }
}
</style>
