<template>
  <div>
    <CardsHorizontal />
    <BannerHorizontal />
  </div>
</template>

<script>
import CardsHorizontal from './VueHorizontal/CardsHorizontal.vue'
import BannerHorizontal from './VueHorizontal/BannerHorizontal.vue'
export default {
  components: {
    CardsHorizontal,
    BannerHorizontal,
  },
}
</script>
