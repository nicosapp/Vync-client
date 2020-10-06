<template>
  <div class="flex items-center justify-between">
    <a
      href="#"
      class="text-gray-500"
      :class="{ 'text-gray-900': $i18n.locale === 'fr' }"
      @click.prevent="$i18n.setLocale(locale)"
    >
      FR
    </a>
    <a
      href="#"
      class="text-gray-500"
      :class="{ 'text-gray-900': $i18n.locale === 'en' }"
      @click.prevent="$i18n.setLocale(locale)"
    >
      EN
    </a>
  </div>
</template>
