<script>
import MainCharacterCard from './MainCharacterCard.vue';

export default {
    components: {
        MainCharacterCard
    },
    data() {
        return {
        }
    },
    props: {
        characters: {
            type: Array,
            required: true
        }
    }
}
</script>


<template>
    <section class="characters-list container">
        <div class="row">
            <div class="col-12">
                <h2>
                    Cards
                </h2>
            </div>
            <div class="col-12">
                <div class="row">
                    <article v-for="character in characters" :key="character.id" class="col-3">
                        <div id="card" class="card" style="width: 100%;">
                            <img class="card-img-top" :src="character.card_images[0].image_url" alt="Card image cap">
                            <div class="card-body">
                                <h5 id="color-white" class="card-title fw-bold">{{ character.name }}</h5>
                                <p class="card-text fs-6">{{ character.type }}</p>
                            </div>
                        </div>
                    </article>
                </div>
            </div>
        </div>
    </section>
</template>


<style lang="scss">

h2{
    text-align: center;
    padding: 1rem;
}

.container {
    background-color: white;
}

#card{
    background-color: #d48f38;
    text-align: center;
    margin-bottom: .5rem;
}

h5{
    text-transform: uppercase;
}

#color-white{
    color: white;
}

</style>