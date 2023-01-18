<template>
  <v-app>
   <v-app-bar ></v-app-bar>
    <v-main>
      <snap-challenge/>
    </v-main>
  </v-app>
</template>

<script>
import SnapChallenge from './components/snapChallenge.vue';

export default {
  name: 'App',

  components: {
    SnapChallenge,
  },

  data: () => ({
    //
  }),
};
</script>
<style lang="scss">
@import './style/main.scss';
</style>
