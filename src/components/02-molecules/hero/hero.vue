<script setup>
    import Text from '@/components/01-atoms/text/text.vue';
    import moment from 'moment';
    const props = defineProps({
        user: Object
    });
</script>

<template>
    <div class="hero">
        <Text class="hero__name">{{ user ? user.name : '' }}</Text>
        <Text class="hero__username">{{ user ? `@${ user.login }` : '' }}</Text>
        <Text class="hero__date-of-joining">{{ user ? moment(user.created_at).format('LL') : '' }}</Text>
    </div>
</template>

<style lang="scss">
    @import '@/styles/variables.scss';
    @import './hero.scss';
</style>