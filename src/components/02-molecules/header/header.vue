<script setup>
    import ThemeSwitcher from '../../01-atoms/theme-switcher/theme-switcher.vue';
    const props = defineProps({
        theme: String
    });
</script>

<template>
    <header class="header">
        <img v-if="theme === 'dark'" class="header__logo" src="@/assets/graphics/logos/logo-devfinder-dark.svg" alt="devfinder">
        <img v-if="theme === 'light'" class="header__logo" src="@/assets/graphics/logos/logo-devfinder-light.svg" alt="devfinder">
        <ThemeSwitcher @click="$emit('toggleTheme')" class="header__theme-switcher" :theme="theme" />
    </header>
</template>

<style lang="scss">
    @import './header.scss';
</style>