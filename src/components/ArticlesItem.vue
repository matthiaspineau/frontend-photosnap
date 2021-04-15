<template>
  <article>
    <div class="a-article">
      <div class="a-article__media" :class="{'inverse' : isInverse}">
        <picture>
          <source media="(max-width: 650px)"
            :srcset="require('@/assets/images/home/' + item.media.mobile)"/>
          <source media="(max-width: 1400px)"
            :srcset="require('@/assets/images/home/' + item.media.tablet)"/>
          <source media="(min-width: 1400px)"
            :srcset="require('@/assets/images/home/' + item.media.desktop)"/>
          <img :src="require('@/assets/images/home/' + item.media.mobile)"/>
        </picture>
      </div>
       <div class="a-article__wrap__text">
        <div class="a-article__text">
            <h1 class="a-article__text__title">{{ item.title }}</h1>
            <p class="a-article__text__description">
            {{ item.description }}
            </p>
            <link-item :linkText="item.link" :onHeader="false"></link-item>
        </div>
      </div>
    </div>
  </article>
</template>

<script>
import LinkItem from '@/components/LinkItem.vue';

export default {
    name: 'ArticlesItem',
    props: {
        item: {
            type: Object,
            default() {
                return {
                    id: 0,
                    title: "",
                    description: "",
                    link: "",
                    media: {
                        mobile: "",
                        tablet: "",
                        desktop: ""
                    }
                }
            }
        },
        isInverse: {
          type: Boolean,
          default: false
        }
    },
    components: {
      LinkItem
    }
}
</script>