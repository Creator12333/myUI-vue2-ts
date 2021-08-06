<template>
  <div id="app">
    <Home></Home>
  </div>
</template>

<script lang="ts">
import { Vue, Component } from 'vue-property-decorator';
import Home from '@/view/Home.vue';

@Component({
  components: {
    Home
  }
})
export default class App extends Vue {}

</script>

<style lang="stylus">

</style>
