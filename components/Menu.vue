<template>
  <button class="menu-button" @click="show = !show">
    <svg
      fill="var(--button-color)"
      class="hamburger"
      viewBox="0 0 100 100"
      width="40"
    >
      <Transition name="slide-up">
        <!-- <Transition name="top"> -->
        <rect
          v-if="!show"
          class="line top"
          width="80"
          height="10"
          x="10"
          y="25"
          rx="5"
        ></rect>
      </Transition>
      <!-- <Transition name="middle"> -->
      <Transition name="middle">
        <rect
          v-if="show"
          class="line"
          width="10"
          height="80"
          x="45"
          y="10"
          rx="5"
        ></rect>
      </Transition>
      <!-- <Transition name="bottom"> -->
      <Transition name="slide-down">
        <rect
          v-if="!show"
          class="line"
          width="80"
          height="10"
          x="10"
          y="65"
          rx="5"
        ></rect>
      </Transition>
    </svg>
  </button>
  <Transition name="menu-slide">
    <div class="menu" v-if="show">
      <NuxtLink to="#" class="container">
        <img class="background" src="/avatar/pattern.png" alt="" />
        <div class="parent">
          <img class="person" src="/avatar/spongebob.png" alt="person" />
        </div>
      </NuxtLink>
      <NuxtLink to="/" class="link menu-item glow pulsate">Home</NuxtLink>
      <NuxtLink to="/" class="link menu-item glow pulsate">Overview</NuxtLink>
      <NuxtLink to="/" class="link menu-item glow pulsate">About</NuxtLink>
      <NuxtLink to="/" class="link menu-item glow pulsate">Contact</NuxtLink>
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
