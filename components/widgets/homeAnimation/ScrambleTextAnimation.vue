<template>
  <div class="flex justify-center items-center">
    <div class="text"></div>
  </div>
</template>

<script>
export default {
  props: {
    dudColor: {
      type: String,
      required: false,
      default: '#A0AEC0',
    },
    phrases: {
      required: true,
      type: Array,
    },
  },
  data() {
    return {
      el: null,
    }
  },
  mounted() {
    this.start()
  },
  methods: {
    constructor(el) {
      this.el = el
      this.chars = '!<>-_\\/[]{}—=+*^?#________'
      this.update = this.update.bind(this)
    },
    setText(newText) {
      const oldText = this.el.textContent
      const length = Math.max(oldText.length, newText.length)
      const promise = new Promise((resolve) => (this.resolve = resolve))
      this.queue = []
      for (let i = 0; i < length; i++) {
        const from = oldText[i] || ''
        const to = newText[i] || ''
        const start = Math.floor(Math.random() * 40)
        const end = start + Math.floor(Math.random() * 40)
        this.queue.push({ from, to, start, end })
      }
      cancelAnimationFrame(this.frameRequest)
      this.frame = 0
      this.update()
      return promise
    },
    update() {
      let output = ''
      let complete = 0
      for (let i = 0, n = this.queue.length; i < n; i++) {
        const { from, to, start, end, _char } = this.queue[i]
        let char = _char
        if (this.frame >= end) {
          complete++
          output += to
        } else if (this.frame >= start) {
          if (!char || Math.random() < 0.28) {
            char = this.randomChar()
            this.queue[i].char = char
          }
          output += `<span class="dud" style="color:${this.dudColor}">${char}</span>`
        } else {
          output += from
        }
      }
      this.el.innerHTML = output
      if (complete === this.queue.length) {
        this.resolve()
      } else {
        this.frameRequest = requestAnimationFrame(this.update)
        this.frame++
      }
    },
    randomChar() {
      return this.chars[Math.floor(Math.random() * this.chars.length)]
    },
    start() {
      const el = document.querySelector('.text')
      this.constructor(el)

      let counter = 0
      const next = () => {
        this.setText(this.phrases[counter]).then(() => {
          setTimeout(next, 1200)
        })
        counter = (counter + 1) % this.phrases.length
      }

      next()
    },
  },
}
</script>
