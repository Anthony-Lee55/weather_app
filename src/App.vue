<script setup>
import { ref } from 'vue';
import SearchField from './components/SearchField.vue';
import WeatherCard from './components/WeatherCard.vue';

const places = ref([])

const addPlace = (data) => {
  places.value.push(data)
}

const deletePlace = (name) => {
  places.value = places.value.filter(p => p.location.name !== name)
}
</script>
<template>
  <main>

    <div class="text-center mb-6">
      {{ new Date().toLocaleDateString('en-us', {
        weekday: 'long',
        year: 'numeric',
        month: 'long',
        day: 'numeric',
      }) }}
    </div>

    <div>
      <SearchField @place-data="addPlace" />
    </div>

    <div class="grid grid-cols-2 gap-4">
      <div v-for="(place, idx) in places" :key="idx">
        <WeatherCard :place="place" @delete-place="deletePlace" />
      </div>
    </div>
  </main>
</template>
