<script setup>
import SearchField from './components/SearchField.vue';
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
      <SearchField />
    </div>
  </main>
</template>
