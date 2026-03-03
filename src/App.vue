<script setup lang="ts">
import Navbar from "./components/Navbar.vue";
import Hero from "./components/Hero.vue";
import Benefits from "./components/Benefits.vue";
import Services from "./components/Services.vue";
import Testimonials from "./components/Testimonials.vue";
// import InstagramFeed from "./components/InstagramFeed.vue";
import Team from "./components/Team.vue";
import Contact from "./components/Contact.vue";
import Footer from "./components/Footer.vue";
import FAQ from "./components/FAQ.vue";
</script>

<template>
  <Navbar />
  <main id="main-content">
    <Hero />
    <Benefits />
    <Services />
    <Testimonials />
    <!-- <InstagramFeed /> -->
    <Team />
    <Contact />
    <FAQ />
  </main>
  <Footer />
</template>
