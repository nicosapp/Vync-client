<template>
  <div class="flex items-center justify-between">
    <a
      v-for="locale in ['fr', 'en']"
      :key="locale"
      href="#"
      class="text-gray-500"
      :class="{ 'text-gray-900': $i18n.locale === locale }"
      @click.prevent="$i18n.setLocale(locale)"
    >
      {{ locale.toUpperCase() }}
    </a>
  </div>
</template>
