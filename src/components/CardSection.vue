<template>
  <section id="music">
    <div class="container">
      <div class="artists-list row gy-4">
        <div class="artists col mx-3" v-for="(album, i) in albums" :key="i">
          <ArtistCard
            :author="album.author"
            :poster="album.poster"
            :title="album.title"
            :year="album.year"
          />
        </div>
      </div>
    </div>
  </section>
</template>

<script>
import ArtistCard from "./ArtistCard.vue";
export default {
  name: "CardSection",
  components: {
    ArtistCard,
  },
  props: {
    albums: Array,
  }
  
};
</script>

<style lang="scss" scoped>
.artists.col {
  flex-basis: calc(20% - 2rem);
  flex-wrap: wrap;
  background-color: #2e3a46;
}
.artists.col:hover {
  cursor: pointer;
  animation: transform 3s ease-out;
  & {
    @keyframes transform {
      0% {
        transform: scale(1);
      }
      50% {
        transform: scale(1.15);
      }
      100% {
        transform: scale(1);
      }
    }
  }
}
</style>