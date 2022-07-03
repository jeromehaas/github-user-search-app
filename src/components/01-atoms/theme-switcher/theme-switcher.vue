<script setup>
    import Text from '@/components/01-atoms/text/text.vue';
    const props = defineProps({
        theme: String
    });
</script>

<template>
    <div class="theme-switcher">
        <i v-if="theme === 'light'" class="theme-switcher__icon icon icon--moon"></i>
        <i v-if="theme === 'dark'" class="theme-switcher__icon icon icon--sun"></i>
        <Text class="theme-switcher__label">{{ theme }}</Text>
    </div>
</template>

<style lang="scss">
    @import '@/styles/variables.scss';
    @import './theme-switcher.scss';
</style>