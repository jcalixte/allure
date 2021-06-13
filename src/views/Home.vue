<template>
  <div class="home columns is-centered">
    <div class="field column is-one-third">
      <div class="control">
        <input
          v-model.number="minute"
          class="input"
          type="number"
          placeholder="minute"
        />
      </div>
    </div>
    <div class="field column is-one-third">
      <div class="control">
        <input
          v-model.number="second"
          class="input"
          type="number"
          placeholder="second"
        />
      </div>
    </div>
  </div>
  <main>{{ allure }} km/h</main>
</template>

<script lang="ts">
import { computed, defineComponent, ref } from 'vue'

export default defineComponent({
  name: 'Home',
  setup() {
    const minute = ref<number | null>(null)
    const second = ref<number | null>(null)

    const allure = computed(() => {
      if (minute.value === null && second.value === null) {
        return '0'
      }

      const time = (minute.value ?? 0) * 60 + (second.value ?? 0)

      const velocity = (1000 / time) * 3.6

      return velocity.toLocaleString('fr', {
        maximumFractionDigits: 2
      })
    })

    return {
      minute,
      second,
      allure
    }
  }
})
</script>

<style scoped>
main {
  font-size: 4rem;
}

.control {
  padding: 1rem;
}
</style>
