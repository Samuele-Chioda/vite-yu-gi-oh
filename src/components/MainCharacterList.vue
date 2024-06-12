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
                <article v-for="character in characters" :key="character.id">
                    <div class="card" style="width: 100%;">
                        <img class="card-img-top" src="" alt="Card image cap">
                        <div class="card-body">
                            <p class="card-text">Some quick example text to build on the card title and make up the bulk
                                of the card's content.</p>
                        </div>
                    </div>
                    {{ character.name }}
                </article>
            </div>
        </div>
    </section>
</template>


<style lang="scss"></style>