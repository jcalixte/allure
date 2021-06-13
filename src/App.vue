<template>
  <div id="app">
    <h1 class="title is-1">Allure min/km</h1>
    <router-view />
  </div>
</template>

<script lang="ts">
import { defineComponent } from 'vue'

export default defineComponent({
  name: 'App'
})
</script>

<style lang="scss">
@import 'styles/app';
</style>
