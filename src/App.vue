<template>
  <v-app>
      <Main/>
    <v-main>
      <router-view> </router-view>
    </v-main>
  </v-app>
</template>

<script>
import Main from './components/Main';

export default {
  name: 'App',

  components: {
    Main,
  },

  data: () => ({
    //
  }),
};
</script>
