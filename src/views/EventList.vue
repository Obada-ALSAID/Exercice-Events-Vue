<script setup>
  import { ref, onMounted } from 'vue';
  import EventCard from '@/components/EventCard.vue';
  import EventService from '@/services/EventService.js';

  const events = ref([])
  const isLoading = ref(false)
  const error = ref(null)

  onMounted(async () => {
    isLoading.value = true
    error.value = null

    try {
      const response = await EventService.getEvents()
      events.value = response.data
    } catch (err) {
      console.error(err)
      error.value = "Impossible de charger les événements."
    } finally {
      isLoading.value = false
    }
  })
</script>

<template>
  <div class="events">
    <p v-if="isLoading">Chargement des événements…</p>
    <p v-else-if="error">{{ error }}</p>
    <EventCard v-for="event in events" :key="event.id" :event="event" />
  </div>
</template>


<style scoped>
  .events {
    display: flex;
    flex-direction: column;
    align-items: center;
  }
</style>