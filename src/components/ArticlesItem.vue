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
            <div class="a-article__text__link">
            <span>{{ item.link }}</span>
            <svg class="a-article__text__arrow" viewBox="0 0 42 14" fill="none" xmlns="http://www.w3.org/2000/svg">
                <path d="M0 7H41.864" />
                <path d="M35.4282 1L41.4282 7L35.4282 13" />
            </svg>
            </div>
        </div>
      </div>
    </div>
  </article>
</template>

<script>
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
    }
}
</script>