<template>
  <div class="p-4 flex gap-4">
    <button class="btn">Hello daisyUI</button>
    <select class="select w-full max-w-xs" v-model="colorMode.preference">
      <option disabled selected>Theme</option>
      <option v-for="theme of themes" :key="theme">{{ theme }}</option>
    </select>
  </div>
  <ul class="menu menu-vertical lg:menu-horizontal bg-base-200 rounded-box">
    <li v-for="link in links"><NuxtLink :to="link.to">{{ link.label }}</NuxtLink></li>
  </ul>
  <RouterView />
</template>

<script setup>
import { _themes as daisyThemes } from '#tailwind-config/daisyui'

const colorMode = useColorMode();

const themes = [
  "system", ...daisyThemes
];

const links = [{
  label: 'Home',
  icon: 'i-heroicons-book-open',
  to: '/'
}, {
  label: 'About',
  icon: 'i-simple-icons-stackblitz',
  to: '/about'
}, {
  label: 'Blog',
  icon: 'i-simple-icons-stackblitz',
  to: '/blog'
}, {
  label: 'Playground',
  icon: 'i-simple-icons-stackblitz',
  to: '/playground'
}, {
  label: 'Playground',
  icon: 'i-simple-icons-stackblitz',
  to: '/playground'
}, {
  label: 'Roadmap',
  icon: 'i-heroicons-map',
  to: '/roadmap'
}, {
  label: 'Pro',
  icon: 'i-heroicons-square-3-stack-3d',
  to: '/pro'
}, {
  label: 'Releases',
  icon: 'i-heroicons-rocket-launch',
  to: 'https://github.com/nuxt/ui/releases',
  target: '_blank'
}]
</script>