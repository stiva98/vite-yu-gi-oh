<script>
import { mergeProps } from 'vue';

export default {
    name: "CardComponent",
    data() {
        return {

        }
    },
    methods: {

    },
    props: {
        character: Object
    }
}
</script>

<template>

<div class="col-2 d-flex flex-column mx-2 my-card mb-2">
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
           
</template>

<style lang="scss" scoped>
@use "../assets/scss/partials/variables.scss" as *;

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

</style>