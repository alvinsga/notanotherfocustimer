<template>
  <v-app>
    <v-main class="d-flex justify-center align-center">
      <HelloWorld />
    </v-main>
    <v-footer class="justify-center">
      <div class="grey--text text-caption">nof*cksgiven inc.</div>
    </v-footer>
  </v-app>
</template>

<script lang="ts">
import { Component, Vue } from "vue-property-decorator";
// import HelloWorld from "@/components/HelloWorld.vue";

@Component({
  components: {
    HelloWorld: () => import("@/components/HelloWorld.vue"),
  },
})
export default class App extends Vue {}
</script>