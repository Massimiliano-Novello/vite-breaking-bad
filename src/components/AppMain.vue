<script>
import AppContent from './AppContent.vue';
import SearchBar from './SearchBar.vue';
import { store } from "../store";
import axios from 'axios';

export default {
    name: "AppMain",
    components: {
        AppContent,
        SearchBar
    },
    data () {
        return {
            store
        }
    },
    methods: {
        getSelectArchetype () {
            const params = {}
             if(this.store.archetypeSelect) {
                params.archetype = this.store.archetypeSelect
             }
             axios.get(store.apiUrl, {
                params
             }).then((resp) => {
                console.log(resp);
                this.store.cards = resp.data.data
             })
        }
    }
}
</script>


<template>
 <main class="main">
    <SearchBar  @search="getSelectArchetype"/>
    <div class="content d-flex justify-content-start align-items-center">
        <div class="card-section row row-cols-5 p-4">
            <AppContent v-for="item in store.cards" :key="item.id" :card="item"/>
        </div>
    </div>
    <h5>{{ store.error }}</h5>
 </main>
</template>

<style lang="scss" scoped>
.main {
    background-color: orange;

    .content {
        width: 70%;
        background-color: white;
        margin: 0 auto;

        .card-section {
            width: 100%;
            height: 100%;
            margin-left: 0;
        }

    }
}

</style>