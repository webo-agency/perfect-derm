<template>
    <div class="relative mb-8">
      <!-- <div 
        class="h-600px bg-fixed bg-top"
        :class="{'max-h-310': isSmallHeader}"
        :style="{ backgroundImage: `url(${imageBanner})` }"
      >
        <img :src="imageBanner" alt="" class="h-full w-full object-cover object-top invisible"/>
      </div> -->

      <div class="container flex flex-row flex-wrap mb-4 mt-2">
        <a :href="('/').concat(this.$i18n.defaultLocale == this.$i18n.locale ? '' : this.$i18n.locale.concat('/'))" class="mr-2">{{ $t('homepage__breadcrumb__title') }}</a>
        <span class="block mr-2">|</span>
        <a class="mr-2">{{ breadcrumb }}</a>
      </div>

      <div class="container text-left p-4">
        <h1 class="font-light text-5xl uppercase" :class="{'mb-4': typeof description === 'string'}">{{ title }}</h1>
        <div v-if="typeof description === 'string'" class="header-desc font-light lg:max-w-1/2" v-html="$md.render(description)"></div>
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
      'image': {
        type: String,
        default: '/images/uploads/natural-lift.jpeg',
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
      'isSmallHeader': {
        type: Boolean,
        default: true,
        required: false
      },
    },
    computed: {
      imageBanner: function(){
        // return require(`~/static${this.image}?resize&size=1920`);
      }
    }
  }
</script>


<style scoped>
  .header-desc >>> p{
    @apply mb-4;
  }
</style>