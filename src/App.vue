<template>
  <v-app>
    <v-main class="justify-center align-center">
      <div class="text-center font-weight-black text-h2 mb-12">Not Another Focus Timer</div>
<div class="d-flex justify-center" >
  <v-btn class="ma-3" depressed dark rounded large color="black">3 minutes</v-btn>
  <v-btn class="ma-3" depressed dark rounded large color="black">5 minutes</v-btn>
  <v-btn class="ma-3" depressed dark rounded large color="black">10 minutes</v-btn>
</div>
    </v-main>
  </v-app>
</template>

<script lang="ts">
import Vue from 'vue';

export default Vue.extend({
  name: 'App',

  components: {

  },

  data: () => ({
    //
  }),
});
</script>
