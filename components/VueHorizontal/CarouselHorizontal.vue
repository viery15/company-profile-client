<template>
  <div>
    <header>
      <div class="header">
        <h1>Events & News</h1>
      </div>
    </header>

    <div class="carousel">
      <vue-horizontal
        ref="horizontal"
        class="horizontal"
        :button-between="false"
        @scroll-debounce="onScrollDebounce"
      >
        <div v-for="item in items" :key="item.id" class="item">
          <img :src="item.img" />
          <div class="content">
            <a :href="item.url" target="_blank"
              ><h4>{{ item.name }}</h4></a
            >
            <p>
              Lorem ipsum dolor sit amet, consectetur adipiscing elit. Donec
              fringilla congue enim, at convallis magna pulvinar vel.
              Suspendisse sed diam mi. Quisque purus velit, commodo non diam
              vitae, semper pharetra purus. Nam non gravida dolor.
            </p>
            <button>Read More</button>
          </div>
        </div>
      </vue-horizontal>

      <div class="dots">
        <div
          v-for="(item, i) in items"
          :key="item.id"
          class="dot"
          :class="{ current: i === index }"
          @click="onIndexClick(i)"
        >
          <div></div>
        </div>
      </div>
    </div>
  </div>
</template>

<script>
import VueHorizontal from 'vue-horizontal'
export default {
  components: { VueHorizontal },
  data() {
    return {
      items: [
        {
          id: 'id1',
          img: 'https://www.tamandayu.com/_assets/images/uploads/promo_list/1382341931_QEbL72a1GfpZwL5ztRoQ.jpg',
          url: '#',
          name: 'What They Say about the Taman Dayu Championship Course',
          description:
            'We have designed a course that fits naturally into the environment, provides a good test of golf for all players and features spectacular views and scenery.',
        },
        {
          id: 'id2',
          img: 'https://www.tamandayu.com/_assets/images/uploads/promo_list/1382341748_wq7g8G1YtPn03OBMNIaX.jpg',
          url: '#',
          name: 'Great Golf in a Glorious Setting: The Taman Dayu Championship 2012',
          description:
            'This is a brilliant golf course…probably the best that I’ve played anywhere in Asia. Clearly I have a score to show for it,” said Sujjan Singh of India as he saluted the immaculate conditions and layout at the Jack Nicklaus-designed Taman Dayu Golf',
        },
        {
          id: 'id3',
          img: 'https://www.tamandayu.com/_assets/images/uploads/promo_list/1382341748_wq7g8G1YtPn03OBMNIaX.jpg',
          url: '#',
          name: 'GOLF COURSE MAINTENANCE',
          description: "We are now into the 4th month of the wet season and  already experiencing more sun shine.  This will have a positive impact to increase ball run on fairways and reduce wet areas, especially in the rough.",
        },
      ],
      hasPrev: false,
      hasNext: false,
      interval: null,
      scrollWidth: 0,
      left: 0,
      progress: 0,
      index: 0,
    }
  },
  mounted() {
    // Custom observe visibility is below
    // Much easier way: https://www.npmjs.com/package/vue-observe-visibility
    // observeVisibility(this.$refs.horizontal.$el, (visible) => {
    //   if (visible) {
    //     this.interval = setInterval(this.play, 5000)
    //   } else {
    //     clearInterval(this.interval)
    //   }
    // })
  },
  destroyed() {
    clearInterval(this.interval)
  },
  methods: {
    onScrollDebounce({ hasNext, hasPrev, scrollWidth, width, left }) {
      this.hasPrev = hasPrev
      this.hasNext = hasNext
      this.scrollWidth = scrollWidth
      this.left = left
      this.progress = left / scrollWidth
      this.index = Math.round(left / width)
    },
    onIndexClick(i) {
      this.$refs.horizontal.scrollToIndex(i)
    },
    play() {
      if (!this.hasNext && this.hasPrev) {
        this.$refs.horizontal.scrollToIndex(0)
        return
      }

      if (this.hasNext) {
        this.$refs.horizontal.next()
      }
    },
  },
}

/**
 * Custom function, much easier way: https://www.npmjs.com/package/vue-observe-visibility
 *
 * @param element to track visibility
 * @param callback: function(boolean) when visibility change
 */
// function observeVisibility(element, callback) {
//   const observer = new IntersectionObserver(
//     (records) => {
//       callback(records.find((record) => record.isIntersecting))
//     },
//     { rootMargin: '10% 0% 10% 0%', threshold: 0.5 }
//   )
//   observer.observe(element)
// }
</script>

<!-- Content Design -->
<style scoped>
.item {
  width: 100%;
  background: #f7fafc;
  overflow: hidden;
  display: flex;
}

img {
  width: 50%;
  object-fit: cover;
}

.content {
  padding: 32px;
}

.content h2 {
  margin-bottom: 8px;
}

.content p {
  margin: 8px 0;
}

button {
  margin-top: 24px;

  padding: 6px 24px;
  font-size: 18px;
  border-radius: 3px;
  background: white;
  font-weight: 600;
  border: 1px solid #333333;
}

.carousel {
  position: relative;
}

.dots {
  position: absolute;
  bottom: 16px;
  left: 0;
  right: 0;
  display: flex;
  justify-content: center;
}

.dot {
  padding: 4px;
  cursor: pointer;
}

.dot > div {
  border-radius: 10px;
  width: 10px;
  height: 10px;
  background: #33333350;
}

.dot:hover > div {
  background: white;
  border: 1px solid black;
}

.dot.current > div {
  border: 3px solid black;
  background: white;
}

.horizontal >>> .v-hl-btn svg {
  box-shadow: none;
  margin: 12px;
}
</style>

<!-- Parent CSS (Container) -->
<style scoped>
main,
header {
  padding: 0 24px;
}

@media (min-width: 768px) {
  main,
  header {
    padding: 0 48px;
  }
}

article {
  padding: 24px 0;
}
</style>
