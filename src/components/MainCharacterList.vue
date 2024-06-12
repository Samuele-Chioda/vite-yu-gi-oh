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
                    Main Chars
                </h2>
            </div>
            <div class="col-12">
                <div class="row">
                    <article v-for="character in characters" :key="character.id" class="col-3">
                        <div class="card" style="width: 100%;">
                            <img class="card-img-top" :src="character.card_images[0].image_url" alt="Card image cap">
                            <div class="card-body">
                                <h5 class="card-title">{{ character.name }}</h5>
                                <p class="card-text">{{ character.desc }}</p>
                            </div>
                        </div>
                    </article>
                </div>
            </div>
        </div>
    </section>
</template>


<style lang="scss">
.container {
    background-color: white;
}
</style>