<template>
  <div class="border border-b-gray-300">
    <div class="nav container flex items-center justify-between">
      <ul class="h-20 flex items-center">
        <li class="logo">
          <nuxt-link to="/" class="flex items-start">
            <div class="text-4xl font-bold text-theme leading-none">VYNC</div>
            <div class="text-gray-500 ml-2">FR</div>
          </nuxt-link>
        </li>
      </ul>
      <ul class="nav nav-menu flex items-end">
        <li>
          <nuxt-link to="electronique">Electronique</nuxt-link>
        </li>
        <li><nuxt-link to="web">Applications web</nuxt-link></li>
        <li><nuxt-link to="equipe">Equipe</nuxt-link></li>
        <li>
          <nuxt-link
            class="btn ml-4 text-white bg-theme px-4 py-2 rounded"
            to="contact"
            >Nous contacter</nuxt-link
          >
        </li>
      </ul>
    </div>
  </div>
</template>

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
</style>
