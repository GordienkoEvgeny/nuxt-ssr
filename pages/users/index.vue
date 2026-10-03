<script setup>
definePageMeta({
    layout: 'users'
})

const { data } = await useFetch('https://dummyjson.com/users')
const users = ref(data.value.users)
</script>
<template>
  <div class="container">
    <h1  class="users">USERS</h1>
    <ul class="d-flex flex-wrap list-unstyled gap-3">
        <li v-for="user in users" :key="user.id">
            <UserLink :user="user"/>
        </li>
    </ul>
  </div>
</template>

<style>
.users {
    color: rgb(238, 14, 205);
}
</style>