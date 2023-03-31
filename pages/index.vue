<template>
  <div class="company-profile">
    <TopBar :side-bar="sideBar" :on-side-bar-click="onSideBarClick" />
    <SideBar :side-bar="sideBar" :on-side-bar-click="onSideBarClick" />
    <main class="container"></main>
  </div>
</template>

<script>
// import TopBar from '~/components/TopBar.vue'
import SideBar from '~/components/SideBar.vue'

export default {
  name: 'CompanyProfile',
  components: {
    // TopBar,
    SideBar,
  },
  data() {
    return {
      sideBar: {
        isCollapsed: true,
      },
    }
  },
  methods: {
    onSideBarClick() {
      this.sideBar.isCollapsed = !this.sideBar.isCollapsed
    },
  },
}
</script>
