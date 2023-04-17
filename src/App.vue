<script>
import AppHeader from './components/AppHeader.vue';
import AppMain from './components/AppMain.vue';
import axios from "axios";
import { store } from "./store"

export default {
  components: {
    AppHeader,
    AppMain
  },
  data () {
    return {
      store
    }
  },
  mounted () {
    axios.get(store.apiUrl).then((resp) => {
      const myData = resp.data.data
      const firstDate = myData.splice(0, 20);
      console.log(firstDate);
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