<script setup>
defineProps({
  day: Object
})

</script>

<template>
  <div class="mb-2 flex items-center justify-between">
    <table class="w-full">
      <tr>
        <td class="w-1/3">{{ new Date(day.date).toLocaleDateString('en-us', { weekday: 'long' }) }}
        </td>

        <td class="w-1/3">
          <img :src="day.condition.icon" alt="icon" width="30" class="mx-auto">
        </td>
        <td class="w-1/3 text-right">{{ Math.round(day.maxTemp_f) }} / {{
          Math.round(day.minTemp_f) }}</td>
      </tr>
    </table>
  </div>
</template>
