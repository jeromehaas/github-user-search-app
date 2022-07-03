<script setup>
    import { ref } from 'vue';
    import Button from '@/components/01-atoms/button/button.vue';
    const input = ref('');
    const props = defineProps({
        error: Boolean
    });
</script>

<template>
    <div class="searchbar">
        <i class="searchbar__icon icon icon--search"></i>
        <input class="searchbar__input" v-model="input" placeholder="Search GitHub username..." spellcheck="false" />
        <p v-if="error" class="searchbar__error">•</p>
        <Button class="searchbar__button button" @click="$emit('updateUsername', input)" >Search</Button>
    </div>
        <Button class="searchbar__fallback-button button" @click="$emit('updateUsername', input)" >Search</Button>
</template>

<style lang="scss">
    @import '@/styles/variables.scss';
    @import '@/styles/central.scss';
    @import './searchbar.scss';
</style>
