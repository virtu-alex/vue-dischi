Descrizione:
MILESTONE -1 Continuate a lavorare nella stessa repo di ieri e aggiungete una select per filtrare i dischi in base al genere: quando l'utente seleziona un genere dalla lista, vengono visualizzati solamente i dischi con il genere corrispondente.
//MILESTONE -2 Aggiungere un ulteriore select che filtra gli album per artista.

<template>
  <div id="app">
    <BaseHeader :genres="genres" />
    <CardSection :albums="albums" />
  </div>
</template>

<script>
import BaseHeader from "./components/BaseHeader";
import CardSection from "./components/CardSection";
import axios from "axios";

export default {
  name: "App",
  components: {
    BaseHeader,
    CardSection,
  },
  data() {
    return {
      albums: [],
    };
  },
  computed: {
    genres() {
      let genres = [];
      for (let album of this.albums) {
        if (!genres.includes(album.genre)) {
          genres.push(album.genre);
        }
      }
      return genres;
    },
  },
  mounted() {
    axios
      .get("https://flynn.boolean.careers/exercises/api/array/music")
      .then((res) => {
        console.log(res.data);
        this.albums = res.data.response;
      });
  },
};
</script>

<style lang="scss">
@import "./assets/scss/style.scss";
body {
  background-color: #1e2d3b;
  padding-top: 130px;
}
</style>
