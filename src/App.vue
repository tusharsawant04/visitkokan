<script setup>
import { RouterLink, RouterView } from 'vue-router'
import HelloWorld from './components/HelloWorld.vue'
import 'bootstrap/dist/css/bootstrap.min.css';
import 'bootstrap';
import navbar from './components/navbar.vue'
import HeroSlider from './components/HeroSlider.vue'
import CitySection from './components/city/CitySection.vue';
import BeachSection from './components/beaches/BeachSection.vue';
</script>

<template>
   <navbar/>
   <HeroSlider/>
       <CitySection />
 <BeachSection />
</template>

