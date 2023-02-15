<template>
  <div class="header">
    <Menu />
    <div class="header-items">
      <NuxtLink to="/" class="inline link header-item">Home</NuxtLink>
      <NuxtLink to="/" class="inline link header-item">Overview</NuxtLink>
      <NuxtLink to="/" class="inline link header-item">About</NuxtLink>
      <NuxtLink to="/" class="inline link header-item">Contact</NuxtLink>
    </div>
  </div>
</template>

<script>

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
