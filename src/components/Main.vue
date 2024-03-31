<script setup>
</script>
<template>
  <div class="container mx-auto">
    <nav class="space-x-2 py-3 bg-slate-50">
      <router-link class="p-2 bg-slate-100 rounded" to="/">Home</router-link>
      <router-link class="p-2 bg-slate-100 rounded" to="/menu">Menu</router-link>
    </nav>
    <router-view />
  </div>

</template>
<style></style>
