<template>
  <div class="sidebar" :class="{ collapsed: sideBar.isCollapsed }">
    <div class="row mb-3">
      <div class="col text-left">
        <button
          class="navbar-toggler"
          type="button"
          @click="clickSideBar"
        >
          <font-awesome-icon :icon="['fas', 'bars']" class="icon alt" />
        </button>
      </div>
    </div>

    <div class="row">
      <div class="col">
        <button
          class="navbar-toggler"
          type="button"
          @click="sideBar.isCollapsed"
        >
          <img src="/logo.png" alt="My Image" />
        </button>
      </div>
    </div>

    <div class="sidebar-menu">
      <ul class="nav flex-column">
        <li class="nav-item">
          <nuxt-link class="nav-link" to="/">Home</nuxt-link>
        </li>
        <li class="nav-item">
          <nuxt-link class="nav-link" to="/about">About Us</nuxt-link>
        </li>
        <li class="nav-item">
          <nuxt-link class="nav-link" to="/services">Taman Dayu Golf</nuxt-link>
        </li>
        <li class="nav-item">
          <nuxt-link class="nav-link" to="/team">The Resorts</nuxt-link>
        </li>
        <li class="nav-item">
          <nuxt-link class="nav-link" to="/contact">2023 Rates</nuxt-link>
        </li>
        <li class="nav-item">
          <nuxt-link class="nav-link" to="/contact">News & Events</nuxt-link>
        </li>
        <li class="nav-item">
          <nuxt-link class="nav-link" to="/contact">Promotions</nuxt-link>
        </li>
      </ul>
    </div>
  </div>
</template>

<script>
export default {
  name: 'SideBar',
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

  data() {
    return {
      isCollapsed: false,
    }
  },

  methods: {
    clickSideBar(){
      this.onSideBarClick();
    }
  }
}
</script>

<style lang="scss">
@import '~bootstrap/scss/bootstrap';

.sidebar {
  position: fixed;
  top: 0;
  bottom: 0;
  left: 0;
  z-index: 100;
  padding: 48px 20px;
  background-color: #f8f9fa;
  overflow-x: hidden;
  overflow-y: auto;
  transition: all 1s;

  ul {
    margin-top: 20px;
  }
}

.navbar-toggler-icon {
  background-color: #121213; /* Change the background color to white */
}

.nav-link {
  color: #343a40 !important;
  font-weight: 500 !important;
  padding: 0.75rem 1.5rem !important;
  text-transform: uppercase;
  border-radius: 5px;
  transition: all 0.3s ease-in-out;

  &.active {
    background-color: #343a40 !important;
    color: #fff !important;
  }

  &:hover {
    background-color: #e9ecef !important;
  }
}

.sidebar-menu {
  transition: all 1s;
}

.sidebar.collapsed {
  padding: 0;
  width: 0;
}
</style>
