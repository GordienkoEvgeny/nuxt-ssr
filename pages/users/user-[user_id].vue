<script setup>
import { useRoute } from 'vue-router';
definePageMeta({
    layout: 'users'
})
const { user_id } = useRoute().params


useHead({
    title: `id: ${user_id}`,
})

const { data } = await useFetch(`https://dummyjson.com/users/${user_id}`)
</script>
<template>
  <div class="container">
    <h1>dynamic page id: {{ user_id}}</h1>
    <p class="user">User: {{ data.firstName  }} {{data.lastName}}</p>
  </div>
</template>

<style>
h1 {
    color: blue
}

.user {
    color: black;
}
</style>