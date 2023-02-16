<template>
  <button class="profile-button" @click="show = !show">
    <div class="container">
      <img class="background" v-if="!show" src="/avatar/pattern.png" alt="" />
      <div class="parent">
        <img
          class="person"
          v-if="!show"
          src="/avatar/spongebob.png"
          alt="person"
        />
        <svg
          class="chevron"
          v-if="show"
          aria-hidden="true"
          fill="none"
          stroke="currentColor"
          stroke-width="1.5"
          viewBox="0 0 24 24"
          xmlns="http://www.w3.org/2000/svg"
        >
          <path
            d="M19.5 8.25l-7.5 7.5-7.5-7.5"
            stroke-linecap="round"
            stroke-linejoin="round"
          ></path>
        </svg>
      </div>
    </div>
  </button>
  <Transition name="menu-slide">
    <div class="profile-menu" v-if="show">
      <div class="avatar-backdrop">
          <div class="container">
            <img class="background" src="/avatar/pattern.png" alt="" />
            <div class="parent">
              <img class="person" src="/avatar/spongebob.png" alt="person" />
            </div>
          </div>
      </div>
      <NuxtLink to="/profile" class="link profile-item">Profile</NuxtLink>
      <NuxtLink to="/" class="link profile-item">Preferences</NuxtLink>
      <NuxtLink to="/" class="link profile-item">Payment History</NuxtLink>
      <NuxtLink to="/" class="link profile-item">Log Out</NuxtLink>
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
