<template>
  <div class="home">
    <!-- Header -->
    <header class="container">
      <div class="h-header">
        <div class="h-header__media">
          <picture>
            <source media="(max-width: 650px)" 
                    :srcset="require('@/assets/images/home/'+home.header.media.mobile)">
            <source media="(max-width: 1400px)" 
                    :srcset="require('@/assets/images/home/'+home.header.media.tablet)">
            <source media="(min-width: 1400px)" 
                    :srcset="require('@/assets/images/home/'+home.header.media.desktop)">
            <img :src="require('@/assets/images/home/'+home.header.media.tablet)">
          </picture>
        </div>
        <div class="h-header__wrap__text">
          <div class="h-header__text">
            <h1 class="h-header__text__title">{{ home.header.title }}</h1>
            <p class="h-header__text__description">{{ home.header.description }}</p>
            <div class="h-header__text__link">
              <span>{{ home.header.link }}</span>
              <svg class="h-header__text__arrow" viewBox="0 0 42 14" fill="none" xmlns="http://www.w3.org/2000/svg">
                <path d="M0 7H41.864" />
                <path d="M35.4282 1L41.4282 7L35.4282 13" />
              </svg>
            </div>
          </div>
        </div>
      </div>
    </header>


    <main class="container">
      <!-- Articles -->
      <section>
        <div class="wrapper__home__articles">
          <articles-item  v-for="(article, index) in home.articles" 
            :key="article.id"
            :item="home.articles[index]" 
            :isInverse="index % 2 == 0 ? false : true"></articles-item>
        </div>
      </section>

      <!-- Products -->
      <section>
        <div class="wrapper__home__products">
          <product-item v-for="(product, index) in home.products" 
            :key="product.id"
            :item="home.products[index]" ></product-item>
        </div>
      </section>
    </main>
 

    <!-- Services -->
    <div class="container">
      <div class="contain__services__home">
        <services-item v-for="(service, index) in home.services" :key="service.id"
        :item="home.services[index]"></services-item>
      </div>
    </div>

  </div>
</template>

<script>
// @ is an alias to /src
// import HelloWorld from '@/components/HelloWorld.vue'
import HomeFile from '@/assets/store/home.json';
import ServicesItem from '@/components/ServicesItem.vue';
import ArticlesItem from '@/components/ArticlesItem.vue';
import ProductItem from '@/components/ProductItem.vue';


export default {
  data() {
    return {
      isActive: false,
      home: {}
    }
  },
  beforeMount() {
    this.home = HomeFile.data
  },
  name: 'Home',
  components: {
    ServicesItem,
    ArticlesItem,
    ProductItem
  }
}
</script>

   