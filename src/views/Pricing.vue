<template>
    <div>
        <!-- Header -->
        <header class="container">
            <div class="h-header">
                <div class="h-header__media">
                <picture>
                    <source media="(max-width: 650px)" 
                            :srcset="require('@/assets/images/pricing/'+pricing.header.media.mobile)">
                    <source media="(max-width: 1400px)" 
                            :srcset="require('@/assets/images/pricing/'+pricing.header.media.tablet)">
                    <source media="(min-width: 1400px)" 
                            :srcset="require('@/assets/images/pricing/'+pricing.header.media.desktop)">
                    <img :src="require('@/assets/images/pricing/'+pricing.header.media.mobile)">
                </picture>
                </div>
                <div class="h-header__wrap__text">
                <div class="h-header__text">
                    <h1 class="h-header__text__title">{{ pricing.header.title }}</h1>
                    <p class="h-header__text__description">{{ pricing.header.description }}</p>
                </div>
                </div>
            </div>
        </header>

        <!-- Main -->
        <main class="container">
            <!-- Cards price -->
            <section class="wrapper__cards__price">
                
                <!-- Nav tabs -->
                <div class="nav-tabs">
                    <span class="nav-tabs__button nav-tabs__button--month"
                    @click="perMonth = true" 
                    :class="{'monthActive' : perMonth}">Monthly</span>
                    <span class="nav-tabs__button nav-tabs__button--year"
                    @click="perMonth = false"
                    :class="{'monthActive' : !perMonth}">Yearly</span>
                </div>
                
                <!-- PriceItem : components -->
                <div class="contain__cards__price">
                    <price-item :price="pricing.cards[0]" :onMonth="perMonth"></price-item>
                    <price-item :price="pricing.cards[1]" :onMonth="perMonth"></price-item>
                    <price-item :price="pricing.cards[2]" :onMonth="perMonth"></price-item>
                </div>
            </section>

            <!-- Compare features : table | tabs -->
            <section class="container wrapper__compare container">
                <h2 class="compare__title">Compare</h2>

                <!-- Table lg -->
                <div class="wrapper__compare__table--lg">
                    <table class="table">
                        <thead class="table__thead">
                            <tr>
                                <th class="table__th table__th--key">{{ pricing.compare.features.title }}</th>
                                <th class="table__th table__th--value ">{{ pricing.compare.basic.title }}</th>
                                <th class="table__th table__th--value">{{ pricing.compare.pro.title }}</th>
                                <th class="table__th table__th--value">{{ pricing.compare.busines.title }}</th>
                            </tr>
                        </thead>
                        <tbody class="table__tbody">
                            
                            <tr v-for="n in 8" :key="n">
                                <td class="table__td table__td--key">{{ pricing.compare.features.keys[n - 1].value }}</td>
                                <td class="table__td table__td--value"><img v-if="pricing.compare.basic.keys[n - 1].value" :src="require('@/assets/images/pricing/desktop/check.svg')" alt="image check"></td>
                                <td class="table__td table__td--value"><img v-if="pricing.compare.pro.keys[n - 1].value" :src="require('@/assets/images/pricing/desktop/check.svg')" alt="image check"></td>
                                <td class="table__td table__td--value"><img v-if="pricing.compare.busines.keys[n - 1].value" :src="require('@/assets/images/pricing/desktop/check.svg')" alt="image check"></td>
                            </tr>
                        </tbody>
                    </table>
                </div>
                
                <!-- Table sm -->
                <div class="wrapper__compare__table--sm">
                    <h3 class="compare__table--sm">The features</h3>

                    <div v-for="n in 8" :key="n"
                    class="sm-table">
                        <span class="sm-table__title">{{ pricing.compare.features.keys[n - 1].value }}</span>
                        <div class="sm-table__row">
                            <div class="sm-table__col">
                                <span class="sm-table__col--key">{{ pricing.compare.basic.title }}</span>
                                <span class="sm-table__col--value">
                                    <img v-if="pricing.compare.basic.keys[n - 1].value" :src="require('@/assets/images/pricing/desktop/check.svg')">
                                </span>
                            </div>
                            <div class="sm-table__col">
                                <span class="sm-table__col--key">{{ pricing.compare.pro.title }}</span>
                                <span class="sm-table__col--value">
                                    <img v-if="pricing.compare.pro.keys[n - 1].value" :src="require('@/assets/images/pricing/desktop/check.svg')">
                                </span>
                            </div>
                            <div class="sm-table__col">
                                <span class="sm-table__col--key">{{ pricing.compare.busines.title }}</span>
                                <span class="sm-table__col--value">
                                    <img v-if="pricing.compare.busines.keys[n - 1].value" :src="require('@/assets/images/pricing/desktop/check.svg')">
                                </span>
                            </div>
                        </div>
                    </div>

                </div>
                
            </section>
        </main>


        <!-- Banner Bottom -->
        <section class="container">
            <banner-bot :imgMobile="bannerBot.banner.media.mobile" 
            :imgTablet="bannerBot.banner.media.tablet" 
            :imgDesktop="bannerBot.banner.media.desktop"></banner-bot>
        </section>
    </div>
</template>

<script>

import PricingFile from '@/assets/store/pricing.json';
import BannerBotFile from '@/assets/store/bannerBot.json';
import BannerBot from '@/components/BannerBot.vue';
import PriceItem from '@/components/PriceItem.vue';


export default {
    data() {
        return {
        isActive: false,
        pricing: {},
        bannerBot: {},
        perMonth: true
        }
    },
    beforeMount() {
        this.pricing = PricingFile.data
        this.bannerBot = BannerBotFile.data
    },
    name: 'Pricing',
      components: {
        BannerBot,
        PriceItem
    }
}
</script>