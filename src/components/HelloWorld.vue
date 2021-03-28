<template>
  <div class>
    <v-container>
      <div class="text-center font-weight-black text-h2 mb-12">
        Not Another Focus Timer
      </div>
      <div class="d-flex justify-center align-center">
        <v-row justify="center">
          <v-btn class="ma-3" depressed dark rounded large color="black"
            >3 minutes</v-btn
          >
          <v-btn class="ma-3" depressed dark rounded large color="black"
            >5 minutes</v-btn
          >
          <v-btn class="ma-3" depressed dark rounded large color="black">
            10 minutes</v-btn
          >
        </v-row>
      </div>
    </v-container>
  </div>
</template>

<script lang="ts">
import { Component, Vue } from "vue-property-decorator";

@Component
export default class HelloWorld extends Vue {}
</script>