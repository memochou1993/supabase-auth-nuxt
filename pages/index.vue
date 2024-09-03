<script setup>
const user = useSupabaseUser();

console.log(user);
</script>

<template>
  <NuxtLink to="/sign-out">
    Sign Out
  </NuxtLink>
</template>
