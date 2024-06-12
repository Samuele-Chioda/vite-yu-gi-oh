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
    <!-- <MainCharacterCard /> -->
    <ul>
        <li v-for="character in characters" :key="characters.id">
            {{ character.name }}
        </li>
    </ul>
</template>


<style lang="scss"></style>