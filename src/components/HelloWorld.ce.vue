<script setup lang="ts">
interface Props {
  title: string
}

const props = defineProps<Props>()

// reactive state
let count = $ref(0)

// functions that mutate state and trigger updates
function increment() {
  count++
}

// lifecycle hooks
onMounted(() => {
  // eslint-disable-next-line no-console
  console.log(`The initial count is ${count}.`)
  // eslint-disable-next-line no-console
  console.log(`The title is ${props.title}.`)
})
</script>

<template>
  <h1 class="text-3xl font-bold text-red-800">
    {{ props.title }}
  </h1>
  <button
    type="button"
    class="inline-flex items-center rounded-md border border-gray-300 bg-white px-4 py-2 text-base font-medium text-gray-700 shadow-sm hover:bg-gray-50 focus:outline-none focus:ring-2 focus:ring-indigo-500 focus:ring-offset-2"
    @click="increment"
  >
    Count is: {{ count }}
  </button>
</template>

<style scoped>
@import "../styles/index.css";
</style>
