<template>
  <div class="artist-card text-center p-2">
    <img :src="poster" :alt="author" class="img-fluid mb-3" />
    <h4>{{ title }}</h4>
    <div class="author">
      <span>{{ author }}</span>
    </div>
    <div class="year">
      <span>{{ year }}</span>
    </div>
  </div>
</template>

<script>
export default {
  name: "artistCard",
  props: {
    poster: String,
    title: String,
    author: String,
    year: String,
  },
};
</script>

<style lang="scss" scoped>
img {
  box-shadow: 0 0 5px 2px black;
  height: 200px;
}

h4 {
  text-transform: capitalize;
  color: white;
}
.author, .year {
  color: grey;
}
</style>