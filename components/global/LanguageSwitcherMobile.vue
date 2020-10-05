<template>
  <div class="flex items-center justify-between">
    <a
      v-for="locale in $i18n.locales.reverse()"
      :key="locale.code"
      href="#"
      class="text-gray-500"
      :class="{ 'text-gray-900': $i18n.locale === locale.code }"
      @click.prevent="$i18n.setLocale(locale.code)"
    >
      {{ locale.name.substring(0, 2).toUpperCase() }}
    </a>
  </div>
</template>
