<template>
  <header>
    <div class="row justify-content-center align-items-center">
      <img class="spotify-logo image-fluid" src="../../spotify.png" alt="" />
    </div>
  </header>
</template>

<script>
export default {
  name: "BaseHeader",
};
</script>

<style lang="scss" scoped>
header {
  height: 80px;
  background-color: #2e3a46;
  position: fixed;
  top: 0;
  left: 0;
  right: 0;
  padding-top: 15px;
  & .spotify-logo {
    width: 300px;
    height: 50px;
  }
}
</style>