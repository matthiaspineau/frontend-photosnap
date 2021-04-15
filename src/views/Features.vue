<template>
    <div>
        <!-- Header -->
        <header class="container">
            <div class="h-header">
                <div class="h-header__media">
                <picture>
                    <source media="(max-width: 650px)" 
                            :srcset="require('@/assets/images/features/'+features.header.media.mobile)">
                    <source media="(max-width: 1400px)" 
                            :srcset="require('@/assets/images/features/'+features.header.media.tablet)">
                    <source media="(min-width: 1400px)" 
                            :srcset="require('@/assets/images/features/'+features.header.media.desktop)">
                    <img :src="require('@/assets/images/features/'+features.header.media.mobile)">
                </picture>
                </div>
                <div class="h-header__wrap__text">
                <div class="h-header__text">
                    <h1 class="h-header__text__title">{{ features.header.title }}</h1>
                    <p class="h-header__text__description">{{ features.header.description }}</p>
                </div>
                </div>
            </div>
        </header>

          <!-- Services -->
        <section class="container">
            <div class="contain__services">
                <services-item v-for="(feature, index) in features.services" :key="feature.id"
                :item="features.services[index]"></services-item>
            </div>
        </section>

        <!-- Banner Bottom -->
        <section class="container">
            <banner-bot :imgMobile="bannerBot.banner.media.mobile" 
            :imgTablet="bannerBot.banner.media.tablet" 
            :imgDesktop="bannerBot.banner.media.desktop"></banner-bot>
        </section>
    </div>
</template>

<script>
import FeaturesFile from '@/assets/store/features.json';
import BannerBotFile from '@/assets/store/bannerBot.json';
import ServicesItem from '@/components/ServicesItem.vue';
import BannerBot from '@/components/BannerBot.vue';


export default {
    data() {
        return {
        isActive: false,
        features: {},
        bannerBot: {}
        }
    },
    beforeMount() {
        this.features = FeaturesFile.data
        this.bannerBot = BannerBotFile.data
    },
    name: 'Features',
    components: {
        ServicesItem,
        BannerBot
    }
}
</script>