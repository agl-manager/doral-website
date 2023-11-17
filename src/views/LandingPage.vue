<template>
  <main
    class="w-full h-screen relative flex flex-col max-h-screen max-w-full overflow-y-auto scroll scroll-smooth"
  >
    <AppNavBar />
    <AppDescription id="home" />
    <DevelopmentInformation />
    <AppLogos />
    <AboutUs id="about_us" />
    <ChoseUs />
    <ProjectsCarrusel id="projects" />
    <JourneyWithUs />
    <CompanyLeaderships id="leadership" />
    <ContactUs id="contact_us" />
    <AppFooter />
  </main>
</template>
<script lang="ts" setup>
import AboutUs from '@/components/AboutUs/AboutUs.vue'
import ChoseUs from '@/components/ChoseUs/ChoseUs.vue'
import ContactUs from '@/components/ContactUs/ContactUs.vue'
import AppDescription from '@/components/Description/AppDescription.vue'
import DevelopmentInformation from '@/components/Development/DevelopmentInformation.vue'
import AppFooter from '@/components/Footer/AppFooter.vue'
import JourneyWithUs from '@/components/Journey/JourneyWithUs.vue'
import CompanyLeaderships from '@/components/Leadership/CompanyLeaderships.vue'
import AppLogos from '@/components/LogoGray/AppLogos.vue'
import AppNavBar from '@/components/NavBar/AppNavBar.vue'
import ProjectsCarrusel from '@/components/Projects/ProjectsCarrusel.vue'
</script>
