<template>
  <div class="hello">
<div class="text-center font-weight-black text-h2 mb-12">Not Another Focus Timer</div>
<div class="d-flex ">
  <button>Hellow</button>
    <button>Hellow</button>
      <button>Hellow</button>
    <button>Hellow</button>
      <button>Hellow</button>
    <button>Hellow</button>
      <button>Hellow</button>
    <button>Hellow</button>
      <button>Hellow</button>
    <button>Hellow</button>
      <button>Hellow</button>
    <button>Hellow</button>
      <button>Hellow</button>
    <button>Hellow</button>
      <button>Hellow</button>
    <button>Hellow</button>
      <button>Hellow</button>
    <button>Hellow</button>

  <!-- <v-btn class="ma-3" depressed dark rounded large color="black">3 minutes</v-btn>
  <v-btn class="ma-3" depressed dark rounded large color="black">5 minutes</v-btn>
  <v-btn class="ma-3" depressed dark rounded large color="black">10 minutes</v-btn> -->
</div>
  </div>
</template>

<script lang="ts">
import { Component, Prop, Vue } from 'vue-property-decorator';

@Component
export default class HelloWorld extends Vue {
  @Prop() private msg!: string;
}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
h3 {
  margin: 40px 0 0;
}
ul {
  list-style-type: none;
  padding: 0;
}
li {
  display: inline-block;
  margin: 0 10px;
}
a {
  color: #42b983;
}
</style>
