<script>
import AppContent from './AppContent.vue';
import { store } from "../store";

export default {
    name: "AppMain",
    components: {
        AppContent
    },
    data () {
        return {
            store
        }
    }
}
</script>


<template>
 <main class="main">
    <select name="" id="">
        <option value="">livello 1</option>
        <option value="">livello 2</option>
        <option value="">livello 3</option>
    </select>
    <div class="content d-flex justify-content-start align-items-center ">
        <div class="card-section row row-cols-5">
            <AppContent />
        </div>
    </div>
 </main>
</template>

<style lang="scss" scoped>
.main {
    height: 700px;
    background-color: orange;

    .content {
        width: 70%;
        background-color: white;
        margin: 0 auto;

        .card-section {
            width: 100%;
            height: 100%;
        }

    }
}

</style>