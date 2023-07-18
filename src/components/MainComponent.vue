<script>
export default {
    name: "MainComponent",
    data() {
        return {

        }
    },
    methods: {

    },
    props: {
        characters: {
            type: Array,
            default: []
        }
    }
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
            <div class="row justify-content-between">
                <div class="col-2 d-flex flex-column mx-2 my-card mb-2" v-for="(character, i) in characters" :key="i">
                    <div>
                        <img :src="character.card_images[0].image_url" :alt="character.name">
                    </div>
                    <div class="container-card">
                        <h2 class="mb-0 text-white text-center">
                            {{ character.name }}
                        </h2>
                        <p class="text-center">
                            {{ character.archetype }}
                        </p>
                    </div>
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
    .container-card > h2 {
        font-weight: bold;
        font-size: small;
        text-transform: uppercase;
    }
    .container-card  {
        font-size: small;
        background-color: $first-bg-color;
        padding: 20px;
        flex-grow: 1;
    }
    img {
        max-width: 100%;
        max-height: 100%;
        object-fit: cover;
    }
    .my-card {
        flex-grow: 1;
    }
}
</style>