<script setup>
    import Text from '@/components/01-atoms/text/text.vue';
    const props = defineProps({
        user: Object
    });
</script>

<template>
    <div class="stats">
        <div class="stats__item item">
            <Text class="item__label">Repos</Text>
            <Text class="item__value">{{ user ? user.public_repos : '' }}</Text>
        </div>
        <div class="stats__item item">
            <Text class="item__label">Followers</Text>
            <Text class="item__value">{{ user ? user.followers : '' }}</Text>
        </div>
        <div class="stats__item item">
            <Text class="item__label">Following</Text>
            <Text class="item__value">{{ user ? user.following : '' }}</Text>
        </div>
    </div>
</template>

<style lang="scss">
    @import '@/styles/variables.scss';
    @import '@/styles/central.scss';
    @import './stats.scss';
</style>