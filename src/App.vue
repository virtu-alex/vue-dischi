<template>
  <div id="app">
    <BaseHeader />
    <CardSection />
  </div>
</template>

<script>
import BaseHeader from "./components/BaseHeader";
import CardSection from "./components/CardSection";
export default {
  name: "App",
  components: {
    BaseHeader,
    CardSection,
  },
};
</script>

<style lang="scss">
@import "./assets/scss/style.scss";
body{
  background-color: #1E2D3B;
  padding-top: 130px;
}

</style>
