<template>
  <main>
    <div class="header">
      <h1>Amenities</h1>
    </div>

    <vue-horizontal class="horizontal">
      <div v-for="item in items" :key="item.id" class="item">
        <div class="card">
          <div class="image" :style="{ background: `url(${item.img})` }"></div>
          <div class="content">
            <div>
              <div class="brand">
                <svg class="icon" viewBox="0 0 24 24">
                  <path
                    d="M19,5v14H5V5H19 M19,3H5C3.9,3,3,3.9,3,5v14c0,1.1,0.9,2,2,2h14c1.1,0,2-0.9,2-2V5C21,3.9,20.1,3,19,3L19,3z"
                  />
                  <path
                    d="M14,17H7v-2h7V17z M17,13H7v-2h10V13z M17,9H7V7h10V9z"
                  />
                </svg>
                <div class="name">{{ item.subtitle }}</div>
              </div>

            </div>
          </div>
        </div>
      </div>
    </vue-horizontal>
  </main>
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
          img: 'https://www.tamandayu.com/_assets/images/uploads/about_us/1510106005_cSiO3Moh6ZvjKQzf2QZD.jpg',
          subtitle: "Jack's Terrace Restaurant",
          description: 'description',
        },
        {
          id: 'id2',
          img: 'https://www.tamandayu.com/_assets/images/uploads/about_us/1595469410_8t6W3rb8JS3drgyLR7Jf.jpg',
          subtitle: "New atmosphere at Jack's Terrace Resto & Lounge",
          description: 'description',
        },
        {
          id: 'id3',
          img: 'https://www.tamandayu.com/_assets/images/uploads/about_us/1614049661_qcJaYq321GlLRzidfpRJ.jpg',
          subtitle: "Sky Terrace Cafe",
          description: 'description',
        },
        {
          id: 'id4',
          img: 'https://www.tamandayu.com/_assets/images/uploads/about_us/1382348937_UHP5AJWNgW0TmVQdSqEp.jpg',
          subtitle: "Country Club Gym",
          description: 'description',
        },
        {
          id: 'id5',
          img: 'https://www.tamandayu.com/_assets/images/uploads/about_us/1511342213_azbI0B5dvYSYxr7r0l5o.jpg',
          subtitle: "Country Club Swimming Pools",
          description: 'description',
        },
        {
          id: 'id6',
          img: 'https://www.tamandayu.com/_assets/images/uploads/about_us/1411612432_yNehckyZAOAihcKXddmJ.jpg',
          subtitle: "Taman Dayu Spa",
          description: 'description',
        },
        {
          id: 'id7',
          img: 'https://www.tamandayu.com/_assets/images/uploads/about_us/1510104965_rAhp7HNi428Jx4s8fTY0.jpg',
          subtitle: "The Pro Shop at Taman Dayu",
          description: 'description',
        },
        {
          id: 'id8',
          img: 'https://www.tamandayu.com/_assets/images/uploads/about_us/1406360359_FUul6miWftWBDMsSqDon.jpg',
          subtitle: 'VIP Lockers',
          description: 'description',
        },
      ],
    }
  },
}
</script>

<!-- Content Design -->
<style scoped>
.card {
  border-radius: 6px;
  overflow: hidden;
  border: 1px solid #e2e8f0;
  height: 100%;
  display: flex;
  flex-direction: column;
}

.image {
  background-position: center !important;
  background-size: cover !important;
  background-repeat: no-repeat !important;
  padding-top: 50%;
}

.content {
  padding: 12px 16px;
  flex-grow: 1;
  display: flex;
  flex-direction: column;
  justify-content: space-between;
}

.brand {
  display: flex;
  align-items: center;
  color: #333333;
}

.brand .icon {
  flex-shrink: 0;
  height: 20px;
  width: 20px;
  fill: currentColor;
}

.brand .name {
  margin-left: 4px;
  font-size: 12px;
  font-weight: 700;
  line-height: 1.5;
}

.title {
  font-size: 14px;
  font-weight: 700;
  line-height: 1.6;
  margin-top: 8px;
  margin-bottom: 8px;
}

.date {
  font-size: 12px;
  font-weight: 500;
  line-height: 1.5;
}
</style>

<!-- Parent CSS (Container) -->
<style scoped>
.header {
  margin-bottom: 16px;
}

main {
  padding: 24px;
}

@media (min-width: 768px) {
  main {
    padding: 48px;
  }
}
</style>

<!-- Responsive Breakpoints -->
<style scoped>
.horizontal {
  --count: 1;
  --gap: 16px;
  --margin: 24px;
}

@media (min-width: 640px) {
  .horizontal {
    --count: 2;
  }
}

@media (min-width: 768px) {
  .horizontal {
    --count: 3;
    --margin: 0;
  }
}

@media (min-width: 1024px) {
  .horizontal {
    --count: 4;
  }
}

@media (min-width: 1280px) {
  .horizontal {
    --gap: 24px;
    --count: 6;
  }
}
</style>

<!--
## Responsive Logic
The margin removes the padding from the parent container and add it into vue-horizontal.
If the gap is less than margin, this causes overflow to show and peeks into the next content for better UX.
You can replace this section entirely for basic responsive CSS logic if you don't want this "peeking" experience
for the mobile web.
Note that this responsive logic is hyper sensitive to your design choices, it's not a one size fit all solution.
var() has only 95% cross browser compatibility, you should convert it to fixed values.

There are 2 set of logic:
0-768 for peeking optimized for touch scrolling.
>768 for navigation via buttons for desktop/laptop users.
-->
<style scoped>
@media (max-width: 767.98px) {
  .item {
    width: calc((100% - (var(--margin) * 2) + var(--gap)) / var(--count));
    padding: 0 calc(var(--gap) / 2);
  }

  .item:first-child {
    width: calc(
      (100% - (var(--margin) * 2) + var(--gap)) / var(--count) + var(--margin) -
        (var(--gap) / 2)
    );
    padding-left: var(--margin);
  }

  .item:last-child {
    width: calc(
      (100% - (var(--margin) * 2) + var(--gap)) / var(--count) + var(--margin) -
        (var(--gap) / 2)
    );
    padding-right: var(--margin);
  }

  .item:only-child {
    width: calc(
      (100% - (var(--margin) * 2) + var(--gap)) / var(--count) + var(--margin) *
        2 - var(--gap)
    );
  }

  .horizontal {
    margin: 0 calc(var(--margin) * -1);
  }

  .horizontal >>> .v-hl-container {
    scroll-padding: 0 calc(var(--margin) - (var(--gap) / 2));
  }

  .horizontal >>> .v-hl-btn {
    display: none;
  }
}

@media (min-width: 768px) {
  .item {
    width: calc((100% - ((var(--count) - 1) * var(--gap))) / var(--count));
    margin-right: var(--gap);
  }
}
</style>
