<script setup>
const count = useState('count', () => 0)

const { data } = await useFetch('/api/example', {
    method: 'post',
    body: {id: 1, name: 'John'}
})
</script>

<template>
  <div class="d-flex flex-column min-vh-100">
    <main class="flex-grow-1 d-flex flex-column justify-content-center align-items-center text-center">
      <h1>HOME page</h1>
      <p>counter {{ count }}</p>
      <button @click="count++">increment</button>

      <p style="color:black">{{ data.message }}</p>
    </main>
  </div>
</template>

<style>
h1 {
    color: red;
}
</style>