<template>
  <div>
    <CardsHorizontal />
    <BannerHorizontal />
    <CarouselHorizontal />
  </div>
</template>

<script>
import CardsHorizontal from './VueHorizontal/CardsHorizontal.vue'
import BannerHorizontal from './VueHorizontal/BannerHorizontal.vue'
import CarouselHorizontal from './VueHorizontal/CarouselHorizontal.vue'
export default {
  components: {
    CardsHorizontal,
    BannerHorizontal,
    CarouselHorizontal,
  },
}
</script>
