<template>
  <div id="app">
    <h1 class="main-title title is-1">Allure</h1>
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

.main-title {
  margin-top: 0.5rem;
}
</style>
