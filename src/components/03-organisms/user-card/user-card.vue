<script setup>
    import Hero from '@/components/02-molecules/hero/hero.vue';
    import Stats from '@/components/02-molecules/stats/stats.vue';
    import Details from '@/components/02-molecules/details/details.vue';
    import Avatar from '@/components/02-molecules/avatar/avatar.vue';
    import Introduction from '@/components/02-molecules/introduction/introduction.vue';
    const  props = defineProps({
        user: Object
    });
</script>

<template>
    <div class="user-card">
        <Avatar class="user-card__avatar" :user="user" />
        <Hero class="user-card__hero" :user="user" />
        <Introduction class="user-card__introduction" :user="user" />
        <Stats class="user-card__stats" :user="user" />
        <Details class="user-card__details" :user="user" />
    </div>
</template>

<style lang="scss">
    @import '@/styles/variables.scss';
    @import './user-card.scss';
</style>