<template>
  <svg
    fill="none"
    xmlns="http://www.w3.org/2000/svg"
    :viewBox="`0 0 100 ${size}`"
    preserveAspectRatio="none"
  >
    <polygon :points="points"></polygon>
  </svg>
</template>
<script>
export default {
  props: {
    direction: {
      required: false,
      type: String,
      default: 'top right',
    },
    size: {
      required: false,
      type: Number,
      default: 10,
    },
  },
  computed: {
    points() {
      if (this.direction === 'top left') return `0 0 0 ${this.size} 104 0`
      else if (this.direction === 'bottom right')
        return `100 0 100 ${this.size} -4 ${this.size}`
      else if (this.direction === 'bottom left')
        return `104 ${this.size} 0 0 0 ${this.size}`
      return `104 ${this.size} 0 0 104 0`
    },
  },
}
</script>
