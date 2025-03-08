<script setup>
  import { ref, onMounted } from 'vue'
  import { supabase } from './lib/supabaseClient'

  const countries = ref([])

  async function getCountries() {
    const { data } = await supabase.from('countries').select()
    instruments.value = data
  }

  onMounted(() => {
    getCountries()
  })
  </script>
 
<template>
  <ul>
    <li v-for="country in countries" :key="country.id">{{ country.name }}</li>
    </ul>
  <h1>Food</h1>
  <PersonalProfile/>
  <food-item/>
  <food-item2/>
  <food-item/>
</template>
 
<style>
  #app > div:hover {
    cursor: pointer;
  }
</style>