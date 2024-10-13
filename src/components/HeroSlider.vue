<template>
  <section class="hero-slider">
    <swiper
      :space-between="0"
      :slides-per-view="1"
      :autoplay="{ delay: 3000, disableOnInteraction: false }"
      pagination
      navigation
      loop
    >
      <!-- Slide 1 -->
      <swiper-slide v-for="(slide, index) in slides" :key="index" class="swiper-slide">
        <div class="hero-slide" :style="{ backgroundImage: `url(${slide.image})` }">
          <div class="hero-overlay">
            <h1>{{ slide.title }}</h1>
            <p>{{ slide.description }}</p>
            <a :href="slide.link" class="btn btn-primary">Learn More</a>
          </div>
        </div>
      </swiper-slide>
    </swiper>
  </section>
</template>

<script setup>
import { Swiper, SwiperSlide } from 'swiper/vue';
import 'swiper/css';
import 'swiper/css/navigation';
import 'swiper/css/pagination';
import { ref } from 'vue';

// Slides data for the hero slider
const slides = ref([
  {
    image: "https://i.ibb.co/sRJJNsz/DALL-E-2024-10-13-21-42-31-A-breathtaking-view-of-the-Konkan-coastline-during-sunset-The-scene-showc.webp",
    title: 'येवा कोकण आपलोच आसा!',
    description: 'Discover the heart of Maharashtra’s paradise.',
    link: '#explore-kokan',
  },
  {
    image: 'https://example.com/slide2.jpg',
    title: 'Adventure Awaits',
    description: 'Discover thrilling adventures in the heart of nature.',
    link: '#adventure',
  },
  {
    image: 'https://example.com/slide3.jpg',
    title: 'Plan Your Trip',
    description: 'Find the best travel plans for an unforgettable experience.',
    link: '#plan-trip',
  },
]);
</script>

<style scoped>
.hero-slider {
  width: 100%;
  height: 100vh;
  position: relative;
}

.swiper-slide {
  width: 100%;
  height: 100%;
}

.hero-slide {
  width: 100%;
  height: 100vh;
  background-size: cover;
  background-position: center;
  display: flex;
  align-items: center;
  justify-content: center;
  position: relative;
}

.hero-overlay {
  background: rgba(0, 0, 0, 0.5);
  padding: 20px;
  color: white;
  text-align: center;
}

.hero-overlay h1 {
  font-size: 3rem;
  margin-bottom: 1rem;
}

.hero-overlay p {
  font-size: 1.5rem;
  margin-bottom: 2rem;
}

.hero-overlay .btn {
  padding: 10px 20px;
  font-size: 1rem;
  background-color: #ff5722;
  border: none;
  color: white;
  text-decoration: none;
  cursor: pointer;
}

.hero-overlay .btn:hover {
  background-color: #e64a19;
}
</style>
