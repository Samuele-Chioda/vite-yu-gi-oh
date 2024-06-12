<script>
import AppSearch from './MainSearch.vue';
import MainCharacterList from './MainCharacterList.vue';
import axios from 'axios';

export default {
    components: {
        AppSearch,
        MainCharacterList
    },
    data() {
        return {
            characters: [],
        }
    },
    methods: {
        getCharacters() {
            axios.get('https://db.ygoprodeck.com/api/v7/cardinfo.php')
                .then((response) => {
                    console.log(response.data.data); 
                    this.characters = response.data.data.slice(0,20);
                })
                .catch((error) => {
                    // handle error
                    console.log(error);
                })
                .finally(() => {
                    // always executed
                });
        }
    },
    created() {
        this.getCharacters();
    }
}
</script>

<template>
    <AppSearch />
    <MainCharacterList :characters="characters" />
</template>

<style lang="scss"></style>
