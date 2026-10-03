<script setup>
const count = useState('count', () => 0)
</script>

<template>
  <div class="d-flex flex-column min-vh-100">
    <!-- Хедер прижат к верху -->
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

            <div>
                <slot/>
            </div>
            
  </div>
</template>

<style>
header a:not(.router-link-exact-active):hover {
  text-decoration: underline;
}

header a.router-link-exact-active {
    color:yellow !important;
    font-weight: 500;
}
</style>