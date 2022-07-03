<script setup>
    const props = defineProps({
        user: Object
    });
</script>

<template>
    <img class="avatar" v-if="user" :src="user ? user.avatar_url : ''" alt="Profile Picture">
</template>

<style lang="scss">
    @import '@/styles/variables.scss';
    @import './avatar.scss';
</style>
