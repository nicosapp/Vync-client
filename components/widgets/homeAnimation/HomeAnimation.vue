<template>
  <div class="flex items-center justify-center">
    <div class="animation-wrapper">
      <div class="sphere-animation">
        <HomeAnimationSphere />
      </div>
    </div>
  </div>
</template>

<script>
import anime from 'animejs/lib/anime.es.js'

export default {
  mounted() {
    this.sphereAnimation()
  },
  methods: {
    fitElementToParent(el, padding) {
      const timeout = null
      function resize() {
        if (timeout) clearTimeout(timeout)
        anime.set(el, { scale: 1 })
        // const pad = padding || 0
        // const parentEl = el.parentNode
        // const elOffsetWidth = el.offsetWidth - pad
        // const parentOffsetWidth = parentEl.offsetWidth
        // const ratio = parentOffsetWidth / elOffsetWidth
        // timeout = setTimeout(anime.set(el, { scale: ratio }), 10)
      }
      resize()
      window.addEventListener('resize', resize)
    },

    sphereAnimation() {
      const sphereEl = document.querySelector('.sphere-animation')
      const spherePathEls = sphereEl.querySelectorAll('.sphere path')
      const pathLength = spherePathEls.length
      // const hasStarted = false
      const aimations = []

      this.fitElementToParent(sphereEl)

      const breathAnimation = anime({
        begin() {
          for (let i = 0; i < pathLength; i++) {
            aimations.push(
              anime({
                targets: spherePathEls[i],
                stroke: {
                  value: ['#07cff6', '#CBD5E0'],
                  duration: 500,
                },
                translateX: [2, -4],
                translateY: [2, -4],
                easing: 'easeOutQuad',
                autoplay: false,
              })
            )
          }
        },
        update(ins) {
          aimations.forEach(function (animation, i) {
            const percent =
              (1 - Math.sin(i * 0.35 + 0.0022 * ins.currentTime)) / 2
            animation.seek(animation.duration * percent)
          })
        },
        duration: Infinity,
        autoplay: false,
      })

      const introAnimation = anime
        .timeline({
          autoplay: false,
        })
        .add(
          {
            targets: spherePathEls,
            strokeDashoffset: {
              value: [anime.setDashoffset, 0],
              duration: 3900,
              easing: 'easeInOutCirc',
              delay: anime.stagger(190, { direction: 'reverse' }),
            },
            duration: 2000,
            delay: anime.stagger(60, { direction: 'reverse' }),
            easing: 'linear',
          },
          0
        )

      const shadowAnimation = anime(
        {
          targets: '#sphereGradient',
          x1: '25%',
          x2: '25%',
          y1: '0%',
          y2: '75%',
          duration: 30000,
          easing: 'easeOutQuint',
          autoplay: false,
        },
        0
      )

      introAnimation.play()
      breathAnimation.play()
      shadowAnimation.play()
    },
  },
}
</script>

<style scoped>
/* .animation-wrapper {
  width: 50%;
} */

.sphere-animation {
  width: 580px;
  height: 580px;
}
</style>
