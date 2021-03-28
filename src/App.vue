<template>
  <v-app class="bcolor">
    <v-main class="d-flex justify-center align-center">
      <MainPage />
    </v-main>
    <v-footer class="justify-center bcolor">
      <a
        href="https://github.com/karmanline/notanotherfocustimer"
        target="_blank"
      >
        <v-img class="mb-3 mt-6" :src="require('@/assets/github.svg')"></v-img>
      </a>
    </v-footer>
  </v-app>
</template>

<script lang="ts">
import { Component, Vue } from "vue-property-decorator";

@Component({
  components: {
    MainPage: () => import("@/components/MainPage.vue"),
  },
  metaInfo: {
    title: "Not Another Focus Timer",
    meta: [
      {
        name: "keywords",
        content: "focus pomodoro timer quick simple easy mimalistic",
      },
      {
        name: "description",
        content: "A simple, minimalistic focus timer",
      },
    ],
  },
})
export default class App extends Vue {}
</script>

<style scoped>
.bcolor {
  background-color: #ffebcd !important;
}
</style>