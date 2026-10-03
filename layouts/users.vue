<script setup>
const count = useState('count', () => 0)
</script>

<template>
  <div class="users-layout">
    <header class="bg-dark p-3">
      <ul class="nav">
        <li class="nav-item">
          <NuxtLink to="/" class="nav-link text-white">Home</NuxtLink>
        </li>
        <li class="nav-item">
          <NuxtLink to="/contact" class="nav-link text-white">Contacts</NuxtLink>
        </li>
        <li class="nav-item">
          <NuxtLink to="/users" class="nav-link text-white">Users</NuxtLink>
        </li>
      </ul>
    </header>

    <!-- Обёртка растягивается и прижимает футер вниз -->
    <main class="flex-grow-1">
      <slot />
    </main>

    <footer class="bg-dark p-3">
      <p class="text-white text-center mb-0">Все права защищены 2026</p>
    </footer>
  </div>
</template>

<style>
header a:not(.router-link-exact-active):hover {
  text-decoration: underline;
}

header a.router-link-exact-active {
  color: yellow !important;
  font-weight: 500;
}

.users-layout {
  color: white;
  display: flex;
  flex-direction: column;
  min-height: 100vh;
}
</style>