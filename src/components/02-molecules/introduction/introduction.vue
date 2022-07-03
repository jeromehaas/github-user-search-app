<script setup>
    import Text from '@/components/01-atoms/text/text.vue';
    const props = defineProps({
        user: Object
    });
</script>

<template>
    <span v-if="user && user.bio">
        <Text class="introduction">{{ user ? user.bio : '' }}</Text>  
    </span>
</template>

<style lang="scss">
    @import '@/styles/variables.scss';
    @import './introduction.scss'; 
</style>