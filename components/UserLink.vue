<script setup>
const { user } = defineProps(['user'])
</script>
<template>
            <NuxtLink :to="`/users/user-${user.id}`" class="btn btn-primary">{{ user.firstName }}</NuxtLink>
</template>