<template>
    <div class="product">
        <div class="product__filtre"></div>
        <div class="product__media">
            <picture>
                <source media="(max-width: 650px)"
                    :srcset="require('@/assets/images/stories/' + item.media.mobile)"/>
                <source media="(min-width: 650px)"
                    :srcset="require('@/assets/images/stories/' + item.media.desktop)"/>
                <img :src="require('@/assets/images/stories/' + item.media.mobile)"/>
            </picture>
        </div>
        <div class="product__text">
            <span class="product__text__date">{{ item.date }}</span>
            <h2 class="product__text__title">{{ item.title }}</h2>
            <h4 class="product__text__author">{{ item.by }}</h4>
            <div class="product__text__link">
                <span>read Story</span>
                <svg class="svg__btn__arrow" viewBox="0 0 42 14" fill="none" xmlns="http://www.w3.org/2000/svg">
                    <path d="M0 7H41.864" />
                    <path d="M35.4282 1L41.4282 7L35.4282 13" />
              </svg>
            </div>
        </div>
    </div>
</template>

<script>
export default {
    name: 'ProductItem',
    props: {
        item: {
            type: Object,
            default() {
                return {
                    id: 0,
                    title: "",
                    by: "",
                    media: {
                        mobile: "",
                        tablet: "",
                        desktop: ""
                    }
                }
            }
        }
    }
}
</script>