<script>
import HeaderComponent from "./components/HeaderComponent.vue";
import MainComponent from "./components/MainComponent.vue";
import axios from "axios";

export default {
  name: "App",
  components: {
    HeaderComponent,
    MainComponent,
  },
  data() {
    return {
      charactersArray: []
    };
  },
  methods: {},

  created() {
    axios
        .get('https://db.ygoprodeck.com/api/v7/cardinfo.php?num=50&offset=0')
        .then(response => {
          this.charactersArray = response.data.data;
          //console.log(response.data.data)
        })
  }
};
</script>

<template>
  <HeaderComponent />

  <MainComponent :characters="charactersArray" />
</template>

<style lang="scss">
@use "assets/scss/main";
</style>
