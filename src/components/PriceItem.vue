<template>
    <div class="price-card" 
    :class="price.theme == 'light' ? 'light' : 'dark'">
        <!-- <div class="price-card__text"> -->
            <h2 class="price-card__title">{{ price.title }}</h2>
            <p class="price-card__description">{{ price.description }}</p>
            <h3 class="price-card__pricing--value">{{ onMonth == true ? price.month.value : price.years.value }}</h3>
            <span class="price-card__pricing--key">{{ onMonth ==  false? price.month.text : price.years.text }}</span>
        <!-- </div> -->
            <span class="price-card__button">{{ price.button }}</span>
    </div>
</template>


<script>
export default {
    props: {
        price: {
            type: Object,
            default() {
                return {}
            }
        },
        onMonth: {
            type: Boolean,
            default: true
        }
    },
    name: 'PriceItem'
}
</script>