<template>
    <div class="btn-link" 
    :class="{'btn-link--heading' : onHeader}">
        <span class="btn-link__text">{{ linkText }}</span>
        <svg class="btn-link__icon" viewBox="0 0 42 14" fill="none" xmlns="http://www.w3.org/2000/svg">
            <path d="M0 7H41.864" />
            <path d="M35.4282 1L41.4282 7L35.4282 13" />
        </svg>
    </div>
</template>

<script>
export default {
    name: 'LinkItem',
    props: {
        linkText: {
            type: String,
            default: 'text link'
        },
        onHeader: {
            type: Boolean,
            default: false
        }

    }
}
</script>