<template>
  <nav class="navbar" style="background-color: #a39161">
    <a class="btn navbar-brand" href="#" @click="clickSideBar">
      <font-awesome-icon :icon="['fas', 'bars']" class="icon alt" />
    </a>
    <div id="navbarNav">
      <ul class="navbar-nav ml-auto">
        <li class="nav-item" style="background-color: white">
          <a
            class="nav-link"
            href="https://staahmax.staah.net/be/indexpackdetail?propertyId=MzkyMg==&individual=true"
            target="_blank"
            >Book Now</a
          >
        </li>
      </ul>
    </div>
  </nav>
</template>

<script>
export default {
  name: 'TopBar',
  props: {
    sideBar: {
      type: Object,
      required: true,
    },
    onSideBarClick: {
      type: Function,
      required: true,
    },
  },
  methods: {
    clickSideBar() {
      this.onSideBarClick()
    },
  },
}
</script>
