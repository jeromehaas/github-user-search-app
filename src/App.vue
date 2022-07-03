<script setup>
import { reactive, ref, watch, onMounted } from 'vue';
import Searchbar from '@/components/02-molecules/searchbar/searchbar.vue';
import Text from '@/components/01-atoms/text/text.vue';
import Stats from '@/components/02-molecules/stats/stats.vue';
import Header from '@/components/02-molecules/header/header.vue'
import UserCard from '@/components/03-organisms/user-card/user-card.vue';
import PageWrapper from '@/components/04-layouts/page-wrapper/page-wrapper.vue';
let username = ref(null);
let user = ref(null);
let error = ref(false);
let theme = ref('light');

onMounted(() => {
  document.title = 'GitHub Search User App';
  username.value = 'octocat'
})

const changeTheme = () => {
  theme.value = theme.value === 'light' ? 'dark' : 'light';
  console.log('theme', theme.value);
};

const fetchUser = async () => {
    const res = await fetch(`https://api.github.com/users/${ username.value }`);
    const data = await res.json();
    if (res.status === 200) {
      error.value = false;
      user.value = data;
    } else {
      error.value = true;
    }
};
watch(username, fetchUser);
watch(theme);

</script>

<template>
  <head>
    <title>GitHub User Search App</title>
  </head>
  <PageWrapper :class="theme === 'dark' && 'page-wrapper--dark'">
    <Header @toggleTheme="changeTheme" :theme="theme" />
    <Searchbar :error="error" @updateUsername="(value) => username = value"/>
    <UserCard :user="user" />
  </PageWrapper>
</template>

<style lang="scss">
  @import '@/styles/central.scss';
</style>
