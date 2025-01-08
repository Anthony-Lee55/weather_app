<script setup>
defineProps({
  place: Object
})
</script>

<template>
  <div class="absolute bg-white.80 backdrop-blur-sm text-slate-200 inset-x-0 bottom-0 rounded-t-lg p-8">
    <div class="flex justify-end mb-10">
      <button @click="$emit('close-info')">
        <i class="fa-solid fa-xmark text-xl"></i>
      </button>
    </div>

    <div class="flex justify-between items-center gap-6 mb-20">
      <div class="text-center flex-1">
        <i class="fa-solid fa-wind mb text-2xl"></i>
        <p class="text-xl font-bold">{{ place.current.wind_mph }} mph</p>
        <p>Wind</p>
      </div>

      <div class="text-center flex-1">
        <i class="fa-solid fa-droplet mb text-2xl"></i>
        <p class="text-xl font-bold">{{ place.current.humidity }}%</p>
        <p>Humidity</p>
      </div>

      <div class="text-center flex-1">
        <i class="fa-solid fa-umbrella mb text-2xl"></i>
        <p class="text-xl font-bold">{{ place.current.precip_in }} in</p>
        <p>Precipitation</p>
      </div>
    </div>

    <div class="flex justify-between items-center gap-6 mb-20">

      <div class="text-center flex-1">
        <i class="fa-solid fa-compass mb text-2xl"></i>
        <p class="text-xl font-bold">{{ place.current.wind_dir }}</p>
        <p>Direction</p>
      </div>

      <div class="text-center flex-1">
        <i class="fa-solid fa-thermometer mb text-2xl"></i>
        <p class="text-xl font-bold">{{ Math.round(place.current.feelslike_f) }}</p>
        <p>Feels</p>
      </div>

      <div class="text-center flex-1">
        <i class="fa-solid fa-sun mb text-2xl"></i>
        <p class="text-xl font-bold">{{ Math.round(place.current.uv) }}</p>
        <p>UV Index</p>
      </div>
    </div>

    <div class="justify-end flex">
      <button @click="$emit('remove-place')">
        <i class="fa-solid fa-trash"></i>
      </button>
    </div>
  </div>
</template>
