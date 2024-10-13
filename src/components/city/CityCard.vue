<template>
  <div class="city-card">
    <img :src="image" alt="City Image" class="city-image" />
    <div class="city-name">{{ cityName }}</div>
  </div>
</template>

<script setup>
defineProps(['cityName', 'image']);
</script>

<style scoped>
.city-card {
  position: relative;
  overflow: hidden;
  width: 300px; /* Set a fixed width for the card */
  border-radius: 10px; /* Rounded corners */
  transition: transform 0.3s;
}

.city-image {
  width: 100%;
  height: auto;
  display: block;
}

.city-name {
  position: absolute;
  bottom: 0;
  left: 0;
  right: 0;
  background-color: rgba(0, 0, 0, 0.7); /* Semi-transparent background */
  color: white;
  padding: 10px;
  text-align: center;
  opacity: 0; /* Hidden by default */
  transition: opacity 0.3s;
}

.city-card:hover {
  transform: scale(1.05); /* Scale up on hover */
}

.city-card:hover .city-name {
  opacity: 1; /* Show name on hover */
}
</style>
