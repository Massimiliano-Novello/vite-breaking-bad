<script>
export default {
    name: "AppContent",
    props: {
        card: Object
    }
}
</script>

<template>
  <div class="card">
    <img src="https://images.ygoprodeck.com/images/cards_small/34541863.jpg" alt="">
    <div class="card-content">
        <h4>Ciao</h4>
        <p>come va</p>
    </div>
  </div>
</template>


<style lang="scss" scoped>
.card {
    .card-content {
        background-color: orange;
    }
}

</style>