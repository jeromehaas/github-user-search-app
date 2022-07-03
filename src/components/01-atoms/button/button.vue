<template>
    <div @click="fetchUser" class="button">
        <slot>Button</slot>
    </div>
</template>

<style lang="scss">
    @import '@/styles/variables.scss';
    @import '@/styles/central.scss';
    @import './button.scss';
</style>