<template>
  <!-- You can find this swiper instance object in current component by the "mySwiper"  -->
  <div class="banner relative h-auto xl:h-800px w-full flex items-end justify-center overflow-hidden" v-swiper:banner="swiperOption">
    <ul class="swiper-wrapper">
      <li class="swiper-slide h-auto" v-if="$t('homepage__banner_1__image') !== ''">
        <img 
          :src="require(`~/static${$t('homepage__banner_1__image')}?resize&size=1920`)" 
          alt="" 
          class="w-full h-full object-cover object-right opacity-50 md:opacity-100 min-h-400"
        />
        <div class="absolute top-auto left-auto right-auto container">
          <div class="md:ml-20 flex flex-row text-left lg:max-w-1/2">
            <div class="flex flex-col">
              <h1 
                class="h1 text-2xl sm:text-5xl md:text-55xl text-primary leading-none uppercase" 
                :class="{
                  'mb-1 md:mb-5': $te('homepage__banner_1__description')
                }"
                v-html="$options.filters.break($t('homepage__banner_1__title'))" 
              />    
              <div 
                class="text-xs md:text-27xl font-light italic text-gray-700"
                v-if="$te('homepage__banner_1__description')"
                :class="{
                  'mb-2 md:mb-8': $te('homepage__banner_1__description')
                }"
                v-html="$md.renderInline(this.$t('homepage__banner_1__description'))"
              />
              <div class="flex-initial w-full">
                <a 
                  v-if="$te('homepage__banner_1__button')"
                  :href="$t('homepage__banner_1__link')"
                  class="link-styled text-base"
                >
                  {{ $t('homepage__banner_1__button') }}
                </a>
              </div>
            </div>
          </div>
        </div>
      </li>
      <li class="swiper-slide h-auto" v-if="$t('homepage__banner_2__image') !== ''">
        <img 
          :src="require(`~/static${$t('homepage__banner_2__image')}?resize&size=1920`)" 
          alt="" 
          class="w-full h-full object-cover object-left opacity-50 md:opacity-100 min-h-400"
        />
        <div class="absolute top-auto left-auto right-auto container">
          <div class="md:ml-20 flex flex-row md:flex-row-reverse text-left lg:max-w-1/2 md:ml-auto">
            <div class="flex flex-col">
              <h2 
                class="h1 text-2xl sm:text-5xl md:text-55xl text-primary leading-none uppercase"
                :class="{
                  'mb-1 md:mb-5': $te('homepage__banner_2__description')
                }" 
                v-html="$options.filters.break($t('homepage__banner_2__title'))"
              />
              <div 
                class="text-base md:text-27xl font-light italic text-gray-700"
                v-if="$te('homepage__banner_2__description')"
                :class="{
                  'mb-2 md:mb-8': $te('homepage__banner_2__description')
                }" 
                v-html="$md.renderInline(this.$t('homepage__banner_2__description'))"
              />
              <div class="flex-initial w-full">
                <a 
                  v-if="$te('homepage__banner_2__button')"
                  :href="$t('homepage__banner_2__link')"
                  class="link-styled text-base"
                >
                  {{ $t('homepage__banner_2__button') }}
                </a>
              </div>
            </div>
          </div>
        </div>
      </li>  
      <li class="swiper-slide h-auto" v-if="$t('homepage__banner_3__image') !== ''">
        <img 
          :src="require(`~/static${$t('homepage__banner_3__image')}?resize&size=1920`)" 
          alt="" 
          class="w-full h-full object-cover object-right opacity-50 md:opacity-100 min-h-400"
        />
        <div class="absolute top-auto left-auto right-auto container">
          <div class="md:ml-20 flex flex-row text-left lg:max-w-1/2">
            <div class="flex flex-col">
              <h2 
                class="h1 text-2xl sm:text-5xl md:text-55xl text-primary leading-none uppercase"
                :class="{
                  'mb-1 md:mb-5': $te('homepage__banner_3__description')
                }"
                v-html="$options.filters.break($t('homepage__banner_3__title'))"
              />
              <div 
                class="text-base md:text-27xl font-light italic text-gray-700"
                v-if="$te('homepage__banner_3__description')"
                :class="{
                  'mb-2 md:mb-8': $te('homepage__banner_3__description') != ''
                }"
                v-html="$md.renderInline(this.$t('homepage__banner_3__description'))"
              />
              <div class="flex-initial w-full">
                <a 
                  v-if="$te('homepage__banner_3__button')"
                  :href="$t('homepage__banner_3__link')"
                  class="link-styled text-base"
                >
                  {{ $t('homepage__banner_3__button') }}
                </a>
              </div>
            </div>
          </div>
        </div>     
      </li>
    </ul>
    <div class="hidden md:block absolute h-full w-full">
      <div class="container h-full w-full flex flex-row items-center">
        <div class="w-20 flex flex-col justify-center mr-16 banner-pagination"></div>
      </div>
    </div>
  </div>
</template>

<script>
  export default {
    name: 'Banner',
    data () {
      return {
        swiperOption: {
          loop: true,
          slidesPerView: 'auto',
          centeredSlides: true,
          spaceBetween: 30,
          // autoplay: {
          //   delay: 4000,
          // },
          pagination: {
            el: '.banner-pagination',
            clickable: true
          }
        }
      }
    }
  }
</script>


<style scoped>
  .swiper-slide {
    text-align: center;
    font-size: 38px;
    font-weight: 700;
    display: flex;
    justify-content: center;
    align-items: center;
    @apply bg-white;
  }

  .swiper-slide.h-auto{
    height: auto;
  }

  .banner-pagination{
    text-align: center;
    transition: 300ms opacity;
    transform: translate3d(0, 0, 0);
    z-index: 10;
  }

  .banner-pagination >>> .swiper-pagination-bullet{
    border-radius: 0;
    height: 6px;
    width: 40px;
    margin-bottom: 10px;
  }

  .banner-pagination >>> .swiper-pagination-bullet.swiper-pagination-bullet-active{
    @apply bg-primary;
    width: 50px;
  }

  .banner-pagination >>> .swiper-pagination-bullet{
    border-radius: 0;
    height: 6px;
    width: 40px;
    margin-bottom: 10px;
  }
</style>