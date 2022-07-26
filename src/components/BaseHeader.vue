<template>
  <header>
    <div class="row">
      <div class="col-12 justify-content-center d-flex">
        <img class="spotify-logo image-fluid" src="../../spotify.png" alt="" />
      </div>
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
  padding-top: 5px;
  & .spotify-logo {
    cursor: pointer;
    width: 300px;
    height: 70px;
    animation: scale 5s linear infinite;
    & {
      @keyframes scale {
        0%{
          transform: scale(1);
        }
        50%{
          transform: scale(1.3);
        }
        100%{
          transform: scale(1);
        }
      }
    }
  }
}
</style>