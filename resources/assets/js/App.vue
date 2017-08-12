<template lang="html">
  <div id="app">
    <app-header></app-header>
    <app-content></app-content>
    <app-footer></app-footer>
  </div>
</template>

<script>
import Header from './components/Header.vue';
import Content from './components/Content.vue';
import Footer from './components/Footer.vue';

export default {
  name: 'app',
  components: {
    'app-header': Header,
    'app-content': Content,
    'app-footer': Footer
  },
  data() {
    return {
      msg: 'vue project'
    }
  }
}
</script>

<style lang="css">
</style>
