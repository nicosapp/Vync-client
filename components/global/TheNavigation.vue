<template>
  <div class="border border-b-gray-300 relative">
    <div class="nav container flex items-center justify-between">
      <ul
        class="h-20 flex items-center justify-between flex-grow lg:flex-grow-0 mx-4 lg:mx-0"
      >
        <li class="logo">
          <nuxt-link to="/" class="flex items-start">
            <div class="text-4xl font-bold text-theme leading-none">VYNC</div>
            <div class="text-gray-500 ml-2">FR</div>
          </nuxt-link>
        </li>
        <li class="lg:hidden">
          <div
            class="burger-menu cursor-pointer relative"
            :class="{ '--open': mobilePanelOpen }"
            @click.prevent="mobilePanelOpen = !mobilePanelOpen"
          >
            <div class="middle-line" />
            <!-- <span class="block h-1 rounded-full bg-gray-400" />
            <span class="block h-1 rounded-full bg-gray-400" />
            <span class="block h-1 rounded-full bg-gray-400" /> -->
          </div>
        </li>
      </ul>
      <ul class="nav nav-menu items-end hidden lg:flex">
        <li>
          <LanguageSwitcher class="px-4" />
        </li>
        <li>
          <nuxt-link to="electronique">{{ $t('Electronique') }}</nuxt-link>
        </li>
        <li>
          <nuxt-link to="web">{{ $t('Applications web') }}</nuxt-link>
        </li>
        <li>
          <nuxt-link to="equipe">{{ $t('Equipe') }}</nuxt-link>
        </li>
        <li>
          <nuxt-link
            class="btn ml-4 text-white bg-theme px-4 py-2 rounded"
            to="contact"
            >{{ $t('Nous contacter') }}</nuxt-link
          >
        </li>
      </ul>
    </div>
    <transition name="mobile-panel">
      <div
        v-if="mobilePanelOpen"
        class="w-full absolute"
        @click="mobilePanelOpen = false"
      >
        <ul
          class="nav nav-menu-mobile mx-4 -mt-4 rounded bg-white"
          style="box-shadow: 0 0 3px lightgrey"
        >
          <li>
            <nuxt-link to="electronique">{{ $t('Electronique') }}</nuxt-link>
          </li>
          <li>
            <nuxt-link to="web">{{ $t('Applications web') }}</nuxt-link>
          </li>
          <li>
            <nuxt-link to="equipe">{{ $t('Equipe') }}</nuxt-link>
          </li>
          <li>
            <nuxt-link to="contact">{{ $t('Nous contacter') }}</nuxt-link>
          </li>
          <li><LanguageSwitcherMobile /></li>
        </ul>
      </div>
    </transition>
  </div>
</template>

<script>
export default {
  data() {
    return {
      mobilePanelOpen: false,
    }
  },
}
</script>
<style scoped lang="scss">
.nav.nav-menu > li > a {
  @apply px-4 py-2;

  &:not(.btn) {
    @apply text-theme font-bold rounded;
    &:hover {
      @apply bg-gray-300;
    }
  }
}
.nav.nav-menu-mobile > li {
  @apply py-2 px-8 py-3 font-semibold border-b border-gray-300;
  &:last-child {
    @apply border-b-0;
  }
}
.burger-menu span {
  transition: all 200ms linear;
}
.burger-menu {
  width: 32px;
  height: 30px;
  .middle-line::after,
  &::before,
  &::after {
    content: '';
    left: 0;
    width: 32px;
    height: 3px;
    transition: all 200ms ease-in-out;
    @apply absolute bg-gray-400 rounded-full;
  }
  &::before {
    top: 0;
  }
  .middle-line::after {
    top: 11px;
  }
  &::after {
    top: 22px;
  }
  &.--open {
    &::before {
      transform: rotate(-45deg);
      transform-origin: top right;
    }
    & .middle-line::after {
      opacity: 0;
    }
    &::after {
      transform: rotate(45deg);
      transform-origin: bottom right;
    }
  }
}
.mobile-panel-enter-active {
  transition: all 300ms ease-in-out;
}

.mobile-panel-enter {
  @apply -mt-6 opacity-0;
}
</style>
