<template>
  <div>
    <cTextHeader 
      :title="$t('media__header__title')"
      :description="$t('media__header__description')"
      :breadcrumb="$t('media__breadcrumb__title')"
    />

    <h2>{{ $t('media__subheader__title') }}</h2>

    <div class="container">
      <ul class="flex flex-row flex-wrap -mx-2">
        <li v-for="(n, indexImage) in tableMedia" :key="indexImage" class="w-full sm:w-1/5 max-h-310 px-2 image-hover" @click="index = indexImage">
          <img :src="tableMedia[indexImage].url" :alt="tableMedia[indexImage].caption" class="object-cover w-full h-auto center tc h-full m-auto cursor-pointer"/>  
        </li>
      </ul>
    </div>
    
    <client-only>
      <LightGallery
        :images="tableMedia"
        :index="index"
        :disable-scroll="true"
        @close="index = null"
      />
    </client-only>

  </div>
</template>

<script>
  import cTextHeader from "~/components/text-header.vue";

  export default {    
    components: {
      cTextHeader
    },
    props: {
      'mainClass': {
        type: String,
        default: '',
        required: false
      }
    },
    computed: {
      tableMedia: function () {
        let tableMedia = [];
        for(let i = 0; i <= parseInt(this.$t('$uniqueKeyIndex___media')); i++) {

          tableMedia.push({
            title: this.$t(`_media__${ i }__caption`),
            url: this.$t(`_media__${ i }__image`)
          });
        } 

        tableMedia.sort(function(a, b){
            var keyA = a.position,
                keyB = b.position;
            // Compare the 2 dates
            if(keyA < keyB) return -1;
            if(keyA > keyB) return 1;
            return 0;
        });

        return tableMedia;
      }
    },
    data() {
      return {
        index: null,
      };
    },
  };
</script>

<style scoped>
  .image-hover{
    position: relative;
  }

  .image-hover:after{
    content: '';
    position: absolute;
    left: 0.5rem;
    right: 0.5rem;
    top: 0;
    bottom: 0;
    background: #000;
    z-index: -1;
  }

  .image-hover img{
    transition: 0.3s;
  }

  .image-hover img:hover{
    opacity: 0.5;
  }
</style>
