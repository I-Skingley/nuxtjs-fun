<script lang="ts" setup>
import "./assets/css/header.css";
import "./assets/css/main.css";
</script>

<template>
  <div>
    <client-only>
      <AppHeader />
    </client-only>
    <NuxtPage />
  </div>
</template>
