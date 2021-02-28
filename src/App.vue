<template>
  <v-app>
      <Home/>
      <sideBar/>
    <v-main>
      <router-view> </router-view>
    </v-main>
  </v-app>
</template>

<script>
import Home from './components/Home';
import sideBar from './components/sideBar';

export default {
  name: 'App',

  components: {
    Home,
    sideBar
  },

  data: () => ({
    //
  }),
};
</script>
