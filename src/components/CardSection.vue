<template>
  <section id="music">
    <div class="container">
      <div class="artists-list row gy-4">
        <div class="artists col pe-3" v-for="(artist, i) in artists" :key="i">
          <ArtistCard
            :author="artist.author"
            :poster="artist.poster"
            :title="artist.title"
            :year="artist.year"
          />
        </div>
      </div>
    </div>
  </section>
</template>

<script>
import axios from "axios";
import ArtistCard from "./ArtistCard.vue";
export default {
  name: "CardSection",
  components: {
    ArtistCard,
  },
  data() {
    return {
      artists: [],
    };
  },
  mounted() {
    axios
      .get("https://flynn.boolean.careers/exercises/api/array/music")
      .then((res) => {
        console.log(res.data);
        this.artists = res.data.response;
      });
  },
};
</script>

<style lang="scss" scoped>
.artists.col {
  flex-basis: 20%;
  flex-wrap: wrap;
  background-color: #2e3a46;
}
</style>