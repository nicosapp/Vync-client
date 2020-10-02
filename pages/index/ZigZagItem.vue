<template>
  <div class="relative">
    <div
      class="absolute text-6xl font-bold text-gray-300"
      style="transform: translate(-50%, -50%); z-index: -1"
    >
      {{ number }}
    </div>
    <div class="text-4xl text-gray-700">{{ text }}</div>
  </div>
</template>
<script>
export default {
  props: {
    number: {
      type: String,
      required: false,
      default: '#1',
    },
    text: {
      type: String,
      required: true,
    },
  },
}
</script>
