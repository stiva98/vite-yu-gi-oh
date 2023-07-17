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
            <div class="row">
                <div class="col-2" v-for="(character, i) in characters" :key="i">
                    <div>
                        <img src="" :alt="character.name">
                    </div>
                    <div>
                        <h2>
                            {{ character.name }}
                        </h2>
                    </div>
                    <div>
                        <p>
                            Specie
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
}
</style>