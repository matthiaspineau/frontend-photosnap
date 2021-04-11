<template>
    <div class="service">
        <div class="service__media">
            <div class="service__media__div">
               <img :src="require('@/assets/images/'+item.media.img)" alt="icon service"> 
            </div>
        </div>
        <div class="service__text">
            <h4 class="service__text__title">{{ item.title }}</h4>
            <p class="service__text__description">{{ item.description }}</p>
        </div>
    </div>
</template>

<script>
export default {
    name: 'ServicesItem',
    props: {
        item: {
            type: Object,
            default() {
                return {
                    title: "",
                    description: "",
                    media: {
                        img: ""
                    }
                }
            }
        }
    }
}
</script>