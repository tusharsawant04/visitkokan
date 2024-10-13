<template>
  <div class="beach-card">
    <img :src="image" alt="Beach Image" class="beach-image" />
    <div class="beach-name">{{ beachName }}</div>
  </div>
</template>

<script setup>
defineProps(['beachName', 'image']);
</script>

<style scoped>
.beach-card {
  position: relative;
  overflow: hidden;
  width: 300px; /* Set a fixed width for the card */
  border-radius: 10px; /* Rounded corners */
  transition: transform 0.3s;
}

.beach-image {
  width: 100%;
  height: auto;
  display: block;
}

.beach-name {
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

.beach-card:hover {
  transform: scale(1.05); /* Scale up on hover */
}

.beach-card:hover .beach-name {
  opacity: 1; /* Show name on hover */
}
</style>
