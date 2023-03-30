<template>
  <div class="company-profile">
    <TopBar />
    <SideBar />
    <main class="container">
      <!-- <SectionTitle title="About Us" />
      <AboutUs />
      <SectionTitle title="Our Team" />
      <Team />
      <SectionTitle title="Services" />
      <Services />
      <SectionTitle title="Contact Us" />
      <ContactUs /> -->
    </main>
    <!-- <Footer /> -->
  </div>
</template>

<script>
import TopBar from '~/components/TopBar.vue'
import SideBar from '~/components/SideBar.vue'
// import Footer from '~/components/Footer.vue'
// import AboutUs from '~/components/AboutUs.vue'
// import Team from '~/components/Team.vue'
// import Services from '~/components/Services.vue'
// import ContactUs from '~/components/ContactUs.vue'
// import SectionTitle from '~/components/SectionTitle.vue'

export default {
  name: 'CompanyProfile',
  components: {
    TopBar,
    SideBar,
    // AboutUs,
    // Team,
    // Services,
    // ContactUs,
    // SectionTitle,
  },
}
</script>
