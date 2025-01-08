<script setup>
import { reactive } from 'vue';

const searchTerm = reactive({
  query: '',
  timeout: null,
  results: null,
})

const handleSearch = () => {
  clearTimeout(searchTerm.timeout)
  searchTerm.timeout = setTimeout(async () => {
    const res = await fetch(`http://api.weatherapi.com/v1/search.json?key=e831dd819fd345b18be155600250801&q=${searchTerm.query}`)

    const data = await res.json()
    console.log(data);

  }, 500);

}

</script>

<template>
  <div>
    <form>
      <div class="bg-white border border-indigo-600/30 rounded-lg shadow-lg flex items-center">
        <i class="fa-solid fa-magnifying-glass p-2 text-indigo-600"></i>
        <input v-model="searchTerm.query" @input="handleSearch" type="text" placeholder="Search for a city"
          class="rounded-r-lg p-2 border-0 outline-0 focus:ring-2 focus:ring-indigo-600 ring-inset w-full" />
      </div>
    </form>
    <div class="bg-white my-2 rounded-lg shadow-lg">
      <div>
        <button class="px-3 my-2 hover:text-indigo-600 hover:font-bold w-full text-left"></button>
      </div>
    </div>
  </div>
</template>
