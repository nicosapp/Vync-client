<template>
  <div>
    <a
      v-for="locale in availableLocales"
      :key="locale.code"
      class="text-gray-600 hover:text-gray-900"
      href="#"
      @click.prevent.stop="setLocale(locale.code)"
      >{{ locale.name.substring(0, 2).toUpperCase() }}</a
    >
  </div>
</template>
<script>
export default {
  computed: {
    availableLocales() {
      return this.$i18n.locales.filter((i) => i.code !== this.$i18n.locale)
    },
  },
  methods: {
    setLocale(code) {
      this.$i18n.setLocale(code)
    },
  },
}
</script>
