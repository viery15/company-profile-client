<template>
  <div class="sidebar" :class="{ collapsed: isCollapsed }">
    <div class="row mb-3">
      <div class="col text-left">
        <button
          class="navbar-toggler"
          type="button"
          @click="isCollapsed = !isCollapsed"
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
          @click="isCollapsed = !isCollapsed"
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
          <nuxt-link class="nav-link" to="/about">About</nuxt-link>
        </li>
        <li class="nav-item">
          <nuxt-link class="nav-link" to="/services">Services</nuxt-link>
        </li>
        <li class="nav-item">
          <nuxt-link class="nav-link" to="/team">Team</nuxt-link>
        </li>
        <li class="nav-item">
          <nuxt-link class="nav-link" to="/contact">Contact</nuxt-link>
        </li>
      </ul>
    </div>
  </div>
</template>

<script>
export default {
  name: 'SideBar',

  data() {
    return {
      isCollapsed: false,
    }
  },
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
  transition: all 0.3s ease-in-out;

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
  // width: 100%;
  // height: 100%;
  // position: fixed;
  // top: 56px;
  // left: 0;
  // padding-top: 15px;
  // background-color: #f7f7f7;
  // overflow-y: auto;
  transition: all 1s;
}

.sidebar.collapsed {
  // width: 56px;
  padding: 0;
  width: 0;
}
</style>
