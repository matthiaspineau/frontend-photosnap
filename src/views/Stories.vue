<template>
  <div>
    <div class="container">
        <header class="s-header">
            <div class="s-header__media">
              <picture>
                <source media="(max-width: 650px)" 
                        :srcset="require('@/assets/images/stories/'+stories.header.media.mobile)">
                <source media="(max-width: 1400px)" 
                        :srcset="require('@/assets/images/stories/'+stories.header.media.tablet)">
                <source media="(min-width: 1400px)" 
                        :srcset="require('@/assets/images/stories/'+stories.header.media.desktop)">
                <img :src="require('@/assets/images/stories/'+stories.header.media.mobile)">
              </picture>
            </div>
            <div class="s-header__wrap__text">
              <div class="s-header__text">
                <h4 class="s-header__text__subtitle">{{ stories.header.subtitle }}</h4>
                <h1 class="s-header__text__title">{{ stories.header.title }}</h1>
                <p class="s-header__text__description">{{ stories.header.description }}</p>
                <div class="s-header__text__info">
                  <span class="s-header__text__date">{{ stories.header.date }} </span>
                  <span class="s-header__text__author">{{ stories.header.author }}</span>
                </div>
                <link-item :linkText="stories.header.link" :onHeader="true"></link-item>
              </div>
            </div>
        </header>
    </div>

    <main>
      <section class="container">
        <div class="wrapper__home__products">
          <product-item
            v-for="(product, index) in products.products"
            :key="product.id"
            :item="products.products[index]"
          ></product-item>
        </div>
      </section>
    </main>
  </div>
</template>

<script>
import ProductsFile from "@/assets/store/products.json";
import StoriesFile from "@/assets/store/stories.json";
import ProductItem from "@/components/ProductItem.vue";
import LinkItem from '@/components/LinkItem.vue';

export default {
  name: "Stories",
  data() {
    return {
      isActive: false,
      products: {},
      stories: {}
    };
  },
  beforeMount() {
    this.products = ProductsFile.data;
    this.stories = StoriesFile.data
  },
  components: {
    ProductItem,
    LinkItem
  },
};
</script>