<template>
  <div>
    <cImageHeader 
      :title="$t('offer__header__title')"
      :image="$t('offer__header__image')"
      :description="$t('offer__header__description')"
      :breadcrumb="$t('offer__breadcrumb__title')"
    />

    <section class="relative container py-4">
      <div class="flex flex-col flex-wrap md:flex-row justify-between text-center md:-mx-4 text-2xl">

        <div class="md:w-1/3 mb-8 lg:mb-0 lg:pb-20 md:px-4 flex flex-col">  
          <cSingleSquare
            main-class="w-full mb-4 flex-1"
            :theme="3"
            :title="$t('offer__category_1__title')"
            link="/category_1"
            :image="$t('offer__category_1__background')"
            data-aos-offset="250"
          />
        </div>
        <div class="md:w-1/3 mb-8 lg:mb-0 lg:pb-20 md:px-4 flex flex-col ">
          <cSingleSquare
            main-class="w-full mb-4 flex-1"
            :theme="3"
            :title="$t('offer__category_2__title')"
            link="/category_2"
            :image="$t('offer__category_2__background')"
            data-aos-offset="250"
          />
        </div>
        <div class="md:w-1/3 mb-8 lg:mb-0 lg:pb-20 md:px-4 flex flex-col ">
          <cSingleSquare
            main-class="w-full mb-4 flex-1"
            :theme="3"
            :title="$t('offer__category_3__title')"
            link="/category_3"
            :image="$t('offer__category_3__background')"
            data-aos-offset="250"
          />
        </div>
        <div class="md:w-1/3 mb-8 lg:mb-0 lg:pb-20 md:px-4 flex flex-col ">  
          <cSingleSquare
            main-class="w-full mb-4 flex-1"
            :theme="3"
            :title="$t('offer__category_4__title')"
            link="/category_4"
            :image="$t('offer__category_4__background')"
          />
        </div>
        <div class="md:w-1/3 mb-8 lg:mb-0 lg:pb-20 md:px-4 flex flex-col ">
          <cSingleSquare
            main-class="w-full mb-4 flex-1"
            :theme="3"
            :title="$t('offer__category_5__title')"
            link="/category_5"
            :image="$t('offer__category_5__background')"
          />
        </div>
        <div class="md:w-1/3 mb-8 lg:mb-0 lg:pb-20 md:px-4 flex flex-col ">
          <cSingleSquare
            main-class="w-full mb-4 flex-1"
            :theme="3"
            :title="$t('offer__category_6__title')"
            link="/category_6"
            :image="$t('offer__category_6__background')"
          />
        </div>
      </div>
    </section>


    <section class="container">
      <h2 class="font-light text-32xl uppercase mb-10">
        {{ $t('offer__section_title__title') }}
      </h2>

      <div 
        class="relative flex flex-row text-left h-450px bg-black md:bg-white text-white md:text-primary"
        data-aos="fade-up"
        data-aos-offset="150"
        data-aos-duration="600"
      >
        <div class="absolute md:relative opacity-25 md:opacity-100 w-full md:w-1/2 h-full md:h-auto overflow-hidden">
          <!-- <img 
            :src="require(`~/static${$t('offer__promotion_line_1__background')}?resize&size=785`)" 
            :alt="$t('offer__promotion_line_1__title')"
            width="785"
            height="523"
            class="h-full w-full object-cover"/> -->
        </div>
        <div class="w-full md:w-1/2 flex flex-col justify-center items-start px-12 md:px-8 lg:px-20">
          <h3 class="mb-4 z-10 uppercase">
            {{ $t('offer__promotion_line_1__title') }}
          </h3>
          <div class="mb-4 font-light text-xl z-10" v-html="$md.render(this.$t('offer__promotion_line_1__description'))"></div>     
          <nuxt-link 
            :to="$t('offer__promotion_line_1__link')"
            class="button z-10"
          >
            {{ $t('offer__promotion_line_2__link_title') }}
          </nuxt-link>
        </div>
      </div>

      <div 
        class="relative flex flex-row text-left h-450px bg-black md:bg-white text-white md:text-primary"
        data-aos="fade-up"
        data-aos-offset="150"
        data-aos-duration="600"
      >
        <div class="absolute md:relative opacity-25 md:opacity-100 w-full md:w-1/2 h-full md:h-auto overflow-hidden order-last">
          <!-- <img 
            :src="require(`~/static${$t('offer__promotion_line_2__background')}?resize&size=785`)" 
            :alt="$t('offer__promotion_line_2__title')" 
            width="785"
            height="523"
            class="h-full w-full object-cover"/> -->
        </div>
        <div class="w-full md:w-1/2 flex flex-col justify-center items-start px-12 md:px-8 lg:px-20">
          <h3 class="mb-4 z-10 uppercase">
            {{ $t('offer__promotion_line_2__title') }}
          </h3>
          <div class="mb-4 font-light text-xl z-10" v-html="$md.render(this.$t('offer__promotion_line_2__description'))"></div>     
          <nuxt-link 
            :to="$t('offer__promotion_line_2__link')"
            class="button z-10"
          >
            {{ $t('offer__promotion_line_2__link_title') }}
          </nuxt-link>   
        </div>
      </div>

      <div 
        class="relative flex flex-row text-left h-450px bg-black md:bg-white text-white md:text-primary"
        data-aos="fade-up"
        data-aos-offset="150"
        data-aos-duration="600"
      >
        <div class="absolute md:relative opacity-25 md:opacity-100 w-full md:w-1/2 h-full md:h-auto overflow-hidden">
          <img 
            :src="require(`~/static${$t('offer__promotion_line_3__background')}?resize&size=785`)" 
            :alt="$t('offer__promotion_line_3__title')"
            width="785"
            height="523" 
            class="h-full w-full object-cover"/>
        </div>
        <div class="w-full md:w-1/2 flex flex-col justify-center items-start px-12 md:px-8 lg:px-20">
          <h3 class="mb-4 z-10 uppercase">
            {{ $t('offer__promotion_line_3__title') }}
          </h3>
          <div class="mb-4 font-light text-xl z-10" v-html="$md.render(this.$t('offer__promotion_line_3__description'))"></div>     
          <nuxt-link 
            :to="$t('offer__promotion_line_3__link')"
            class="button z-10"
          >
            {{ $t('offer__promotion_line_2__link_title') }}
          </nuxt-link>
        </div>
      </div>
    </section>
  </div>
</template>

<script>
  import cSingleSquare from "~/components/single-square.vue";
  import cImageHeader from "~/components/image-header.vue";

  export default {    
    components: {
      cSingleSquare,
      cImageHeader
    },
    props: {
      'mainClass': {
        type: String,
        default: '',
        required: false
      }
    }
  };
</script>
