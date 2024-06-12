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
                .then(function (response) {
                    // handle success
                    console.log(response);
                })
                .catch(function (error) {
                    // handle error
                    console.log(error);
                })
                .finally(function () {
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
    <MainCharacterList />
</template>


<style lang="scss"></style>