<script setup lang="ts">
import Loading from "./components/Loading.vue";
import AppContainer from './components/containers/AppContainer.vue';
import Hero from "./components/main/Hero.vue";
import UserProvider from './components/providers/UserProvider.vue';
import Navbar from './components/main/Navbar.vue';
import About from './components/main/About.vue';
import Education from './components/main/Education.vue';
import Skills from "./components/main/Skills.vue";
import AcademicResults from "./components/main/AcademicResults.vue";
import Contact from './components/main/Contact.vue';
import Footer from './components/main/Footer.vue';
import ScrollToTop from "./components/ScrollToTop.vue";
import useLoading from "./hooks/useLoading.ts";

const { isLoading } = useLoading(3);
</script>

<template>
  <AppContainer v-if="isLoading" classname="h-screen w-full flex items-center justify-center">
    <Loading />
  </AppContainer>
  <AppContainer v-else>
    <UserProvider>
      <Hero />
      <Navbar />
      <About />
      <Education />
      <Skills />
      <AcademicResults />
      <Contact />
      <ScrollToTop />
      <Footer />
    </UserProvider>
  </AppContainer>
</template>
