<script setup>
    import Text from '@/components/01-atoms/text/text.vue';
    const props = defineProps({
        user: Object
    })
</script>

<template>
    <div class="details">
        <div v-if="user" class="details__item item">
            <i class="item__icon icon icon--location"></i>
            <Text class="item__text">{{ user.location ? user.location : 'Not Available' }}</Text>
        </div> 
        <div v-if="user" class="details__item item">
            <i class="item__icon icon icon--twitter"></i>
            <Text class="item__text">{{ user.twittername ? user.twittername : 'Not Available' }}</Text>
        </div>
        <div v-if="user" class="details__item item">
            <i class="item__icon icon icon--link"></i>
            <a class="item__link" href="{{ user.blog }}">
                <Text class="item__text">{{ user.blog ? 'Blog' : 'Not Available' }}</Text>
            </a>
        </div>
        <div v-if="user" class="details__item item">
            <i class="item__icon icon icon--building"></i>
            <Text class="item__text">{{ user.company ? user.company : 'Not Available' }}</Text>
        </div>
    </div>
</template>

<style lang="scss">
    @import '@/styles/variables.scss';
    @import './details.scss';
</style>