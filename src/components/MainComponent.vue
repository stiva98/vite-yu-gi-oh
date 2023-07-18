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
                <option v-for="(singleSelectArray, i) in store.selectArray" :key="i" 
                :value="singleSelectArray.archetype_name">
                {{ singleSelectArray.archetype_name}}
            </option>
            </select>
        </div>
        <div class="container bg-white">
            <div class="found-cards bg-black">
                <p class="text-white p-2">
                    Found {{ store.charactersArray.length}} Cards
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