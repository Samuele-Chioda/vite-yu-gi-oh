<script>
import { store } from '../store.js'

export default {
    data() {
        return {
            store,
        }
    }
}
</script>


<template>
    <div class="container mt-4">
        <div class="row">
            <div class="col-10">
                <div class="form-floating mb-3">
                    <input type="text" class="form-control" id="floatingInput" placeholder="search a type" v-model="store.searchedText">
                    <label for="floatingInput">Search type</label>
                </div>
            </div>
            <div class="button col-2">
                    <button class="fs-3 btn btn-primary p-2" @click="$emit('searched')">
                        Search!
                    </button>
                </div>
        </div>
    </div>
</template>


<style lang="scss" scoped></style>