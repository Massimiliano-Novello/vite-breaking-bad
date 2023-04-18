<script>
import AppHeader from './components/AppHeader.vue';
import AppMain from './components/AppMain.vue';
import axios from "axios";
import { store } from "./store"

export default {
  components: {
    AppHeader,
    AppMain,
  },
  data () {
    return {
      store: store
    }
  },
  mounted () {
    axios.get(store.apiUrl).then((resp) => {
      this.store.cards = resp.data.data
    })
  }
}

</script>


<template>
<AppHeader />
<AppMain />

</template>



<style lang="scss">
@use "./styles/general.scss"
</style>