<script>
import AppSearch from './MainSearch.vue';
import MainCharacterList from './MainCharacterList.vue';
import axios from 'axios';
import { store } from '../store.js'

export default {
    components: {
        AppSearch,
        MainCharacterList
    },
    data() {
        return {
            store,
            isLoades: false,
            characters: [],
        }
    },
    methods: {
        info() {
            console.log('info');
            console.log(this.store.searchedText);
        },
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
    <main>
        <AppSearch @searched="info" />
        <MainCharacterList :characters="characters" />
    </main>
</template>

<style lang="scss" scoped>
</style>
