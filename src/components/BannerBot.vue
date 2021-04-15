<template>
    <div class="banner-bot">
        <div class="banner-bot__media">
             <picture>
                <source media="(max-width: 650px)" 
                        :srcset="require('@/assets/images/shared/'+imgMobile)">
                <source media="(max-width: 1400px)" 
                        :srcset="require('@/assets/images/shared/'+imgTablet)">
                <source media="(min-width: 1400px)" 
                        :srcset="require('@/assets/images/shared/'+imgDesktop)">
                <img :src="require('@/assets/images/shared/'+imgMobile)">
            </picture>
        </div>
        <div class="banner-bot__text">
            <h1 class="banner-bot__text__title">{{ title }}</h1>
            <link-item :linkText="'Get an invite'" :onHeader="true"></link-item>
        </div>
    </div>
</template>

<script>
import LinkItem from '@/components/LinkItem.vue';

export default {
    name: 'BannerBot',
    props: {
        title: {
            type: String,
            default: "We’re in beta. Get your invite today!"
        },
        imgMobile: {
            type: String,
            default: ""
        },
        imgTablet: {
            type: String,
            default: ""
        },
        imgDesktop: {
            type: String,
            default: ""
        }
    },
    components: {
        LinkItem
    }
}
</script>