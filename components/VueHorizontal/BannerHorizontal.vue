<template>
  <main>
    <div class="header">
      <h1>The Resorts</h1>
    </div>

    <vue-horizontal class="horizontal">
      <div v-for="item in items" :key="item.id" class="item">
        <div
          class="content"
          :style="{ background: `url(${item.img})` }"
        >
          <div class="aspect-ratio"></div>
          <div class="overlay">
            <h2>{{ item.title }}</h2>
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
          title: "The Villas",
          img: "https://www.tamandayu.com/_assets/images/uploads/about_us/1382349333_YgjumJfBRXouudb5XQpt.jpg"
        },
        {
          title: "The Bungalows",
          img: "https://www.tamandayu.com/_assets/images/uploads/about_us/1382349350_3sZtRNBNH2i2Yf7c0LTp.jpg"
        },
        {
          title: "The Hotel",
          img: "https://www.tamandayu.com/_assets/images/uploads/about_us/1580352468_ujzOFodFRuwiAkfHa7sg.jpg"
        },
      ],
    }
  },
}
</script>

<!-- Content Design -->
<style scoped>
.content {
  background-position: center !important;
  background-size: cover !important;
  background-repeat: no-repeat !important;
  position: relative;
  border-radius: 5px;
  overflow: hidden;
}

.aspect-ratio {
  padding-top: 60%;
}

.overlay {
  position: absolute;
  top: 0;
  bottom: 0;
  left: 0;
  right: 0;
  background: #00000010;
  display: flex;
  align-items: center;
  justify-content: center;
  text-align: center;
  padding: 24px;
}

.overlay > * {
  color: white;
}
</style>

<!-- Parent CSS (Container) -->
<style scoped>
.header {
  margin-bottom: 24px;
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
    --count: 2;
    --margin: 0;
  }
}

@media (min-width: 1024px) {
  .horizontal {
    --count: 3;
  }
}

@media (min-width: 1280px) {
  .horizontal {
    --gap: 24px;
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
