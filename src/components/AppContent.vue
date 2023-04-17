<script>
export default {
    name: "AppContent",
    props: {
        card: Object
    }
}
</script>

<template>
  <div class="card gy-3">
    <img :src="card.card_images[0].image_url_small" alt="">
    <div class="card-content text-center px-2">
        <h4 class="my-3">{{ card.name }}</h4>
        <p>{{ card.archetype }}</p>
    </div>
  </div>
</template>


<style lang="scss" scoped>
.card {
    border: none;
    .card-content {
        background-color: orange;
        height: 100%;

        h4 {
            font-size: 1rem;
            color: white;
        }

        p {
            font-size: .9rem;
        }
    }
}

</style>