<template>
  <div class="header">
    <button class="menu-button" @click="show = !show">
      <svg
        fill="var(--button-color)"
        class="hamburger"
        viewBox="0 0 100 100"
        width="40"
      >
        <rect
          v-if="!show"
          class="line"
          width="80"
          height="10"
          x="10"
          y="15"
          rx="5"
        ></rect>
        <rect
          v-if="!show"
          class="line"
          width="80"
          height="10"
          x="10"
          y="45"
          rx="5"
        ></rect>
        <rect
          v-if="!show"
          class="line"
          width="80"
          height="10"
          x="10"
          y="75"
          rx="5"
        ></rect>
      </svg>
    </button>
    <div class="header-items">
      <NuxtLink to="/" class="inline link header-item">Home</NuxtLink>
      <NuxtLink to="/" class="inline link header-item">Overview</NuxtLink>
      <NuxtLink to="/" class="inline link header-item">About</NuxtLink>
      <NuxtLink to="/" class="inline link header-item">Contact</NuxtLink>
    </div>
  </div>
  <Transition name="menu-slide">
    <div class="menu" v-if="show">
      <NuxtLink to="/" class="menu-item">Home</NuxtLink>
      <NuxtLink to="/" class="menu-item">Overview</NuxtLink>
      <NuxtLink to="/" class="menu-item">About</NuxtLink>
      <NuxtLink to="/" class="menu-item">Contact</NuxtLink>
    </div>
  </Transition>
</template>

<script>
export default {
  data() {
    return {
      show: false,
    };
  },
};
</script>
