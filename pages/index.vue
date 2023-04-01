<template>
  <div class="company-profile">
    <TopBar :side-bar="sideBar" :on-side-bar-click="onSideBarClick" />
    <SideBar :side-bar="sideBar" :on-side-bar-click="onSideBarClick" />
    <VideoHeader />
    <HomeContent />
    <main class="container"></main>
  </div>
</template>
<script>
export default {
  name: 'CompanyProfile',
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
