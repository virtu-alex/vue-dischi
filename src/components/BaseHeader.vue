<template>
  <header>
    <div class="row">
      <div class="col-12 justify-content-between d-flex px-5">
        <img
          class="spotify-logo image-fluid px-3"
          src="../../spotify.png"
          alt=""
        />
        <select @change="genreChanged($event)" class="px-3" name="select" id="">
          <option value="All">All</option>
          <option v-for="(genre, i) in genres" :key="i" :value="genre">
            {{ genre }}
          </option>
        </select>
      </div>
    </div>
  </header>
</template>

<script>
export default {
  name: "BaseHeader",
  props: {
    genres: Array,
  },
  methods: {
    genreChanged(event) {
      const value = event.target.value
      this.$emit("genre-changed", value);
    },
  },
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
        0% {
          transform: scale(1);
        }
        50% {
          transform: scale(1.3);
        }
        100% {
          transform: scale(1);
        }
      }
    }
  }
}
</style>