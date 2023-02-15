<template>
  <div class="header">
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
    <div class="header-items">
      <NuxtLink to="/" class="inline link header-item">Home</NuxtLink>
      <NuxtLink to="/" class="inline link header-item">Overview</NuxtLink>
      <NuxtLink to="/" class="inline link header-item">About</NuxtLink>
      <NuxtLink to="/" class="inline link header-item">Contact</NuxtLink>
    </div>
  </div>
  <Transition name="menu-slide">
    <div class="menu" v-if="show">
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

const pos = { x: 0, y: 0 };

const saveCursorPosition = function (x, y) {
  pos.x = (x / window.innerWidth).toFixed(2);
  pos.y = (y / window.innerHeight).toFixed(2);
  document.documentElement.style.setProperty("--x", pos.x);
  document.documentElement.style.setProperty("--y", pos.y);
};

document.addEventListener("mousemove", (e) => {
  saveCursorPosition(e.clientX, e.clientY);
});
</script>
