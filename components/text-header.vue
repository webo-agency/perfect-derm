<template>
  <div class="relative">
    <hr class="mb-2">
    <div class="container flex flex-row flex-wrap mb-4">
      <a :href="('/').concat(this.$i18n.defaultLocale == this.$i18n.locale ? '' : this.$i18n.locale.concat('/'))" class="mr-2">{{ $t('homepage__breadcrumb__title') }}</a>
      <span class="block mr-2">|</span>
      <a class="mr-2">{{ breadcrumb }}</a>
    </div>

    <div class="container text-left p-4">
      <h1 class="font-light text-5xl uppercase mb-2">{{ title }}</h1>
      <div v-if="typeof description === 'string'" v-html="$md.render(description)"></div>
    </div>
  </div>
</template>

<script>
  export default {
    name: 'cImageHeader',
    props: {
      'title': {
        type: String,
        default: '',
        required: false
      },
      'description': {
        type: String,
        required: false
      },
      'breadcrumb': {
        type: String,
        required: false
      },
    },
  }
</script>

<style scoped>

</style>