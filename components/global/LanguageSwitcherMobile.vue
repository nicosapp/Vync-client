<template>
  <div class="flex items-center justify-between">
    <a
      href="#"
      class="text-gray-500"
      :class="{ 'text-gray-900': isActive('fr') }"
      @click.prevent="$i18n.setLocale('fr')"
    >
      FR
    </a>
    <a
      href="#"
      class="text-gray-500"
      :class="{ 'text-gray-900': isActive('en') }"
      @click.prevent="$i18n.setLocale('en')"
    >
      EN
    </a>
  </div>
</template>

<script>
export default {
  methods: {
    isActive(code) {
      return this.$i18n.locale === code
    },
  },
}
</script>
