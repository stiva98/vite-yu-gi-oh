<script>
import CardComponent from './CardComponent.vue';
import { store } from "../store";

export default {
    name: "MainComponent",
    components: {
    CardComponent
  },
    data() {
        return {
            store
        }
    },
    methods: {

    },
}
</script>

<template>
    <main>
        <div class="container">
            <select class="form-select" aria-label="Default select example">
                <option selected>Alien</option>
                <option value="1">One</option>
                <option value="2">Two</option>
                <option value="3">Three</option>
            </select>
        </div>
        <div class="container bg-white">
            <div class="found-cards bg-black">
                <p class="text-white p-2">
                    Found 39 Cards
                </p>
            </div>
            <div class="row justify-content-between" v-if="store.charactersArray.length == store.variablesArray">
                <CardComponent v-for="(character, i) in store.charactersArray" :key="i" :character="character"/>
            </div>

            <div v-else class="text-center mt-5">
                <div class="spinner-grow text-warning my-loader" role="status">
                    <span class="visually-hidden">Loading...</span>
                </div>
            </div>

        </div>
    </main>
</template>

<style lang="scss" scoped>
@use "../assets/scss/partials/variables.scss" as *;
main {
    background-color: $first-bg-color;

    .container {
        padding: 20px;
    }
    .form-select {
        width: 200px;
    }
    .my-loader {
        width: 100px;
        height: 100px;
    }
}
</style>c