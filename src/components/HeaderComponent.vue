<script>
export default {
    name: "HeaderComponent",
    data() {
        return {

        }
    },
    methods: {

    }
}
</script>

<template>
    <header>
        <div class="container-fluid">
            <div class="row">
                <div class="col-1">
                    <img src="../assets/img/yugioh-logo.png" alt="Yu-Gi-Oh">
                </div>
                <div class="col-auto">
                    <h1>
                        Yu-Gi-Oh API
                    </h1>
                </div>
            </div>
        </div>
    </header>
</template>

<style lang="scss" scoped>
img {
    width: 80px;
}

</style>