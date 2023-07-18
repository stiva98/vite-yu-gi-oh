<script>
import HeaderComponent from "./components/HeaderComponent.vue";
import MainComponent from "./components/MainComponent.vue";
import axios from "axios";
import { store } from "./store";

export default {
  name: "App",
  components: {
    HeaderComponent,
    MainComponent,
  },
  data() {
    return {
      store
    };
  },
  methods: {},

  created() {
    axios
        .get('https://db.ygoprodeck.com/api/v7/cardinfo.php?num=50&offset=0')
        .then(response => {
          this.store.charactersArray = response.data.data;
          //console.log(response.data.data)
        })
    axios
        .get('https://db.ygoprodeck.com/api/v7/archetypes.php')
        .then(response => {
          this.store.selectArray = response.data;
          //console.log(response.data.data)
        })
  }
};
</script>

<template>
  <HeaderComponent />

  <MainComponent />
</template>

<style lang="scss">
@use "assets/scss/main";
</style>
