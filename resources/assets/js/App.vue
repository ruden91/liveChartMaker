<template lang="html">
  <v-app>
    <v-navigation-drawer v-model="sideNav">
      <v-list>
        <v-list-tile>
          <v-list-tile-action>
            View meetups
          </v-list-tile-action>
          <v-list-tile-content>
          </v-list-tile-content>
        </v-list-tile>
      </v-list>
    </v-navigation-drawer>
    <v-toolbar dark class="indigo lighten-1">
      <v-toolbar-side-icon
        @click.native.stop="sideNav = !sideNav"
        class="hidden-sm-and-up"
      ></v-toolbar-side-icon>
      <v-toolbar-title>Webruden</v-toolbar-title>
      <v-spacer></v-spacer>
      <v-toolbar-items class="hidden-xs-only">
        <v-btn flat>
          View Meetups
        </v-btn>
      </v-toolbar-items>
    </v-toolbar>
    <app-content></app-content>
    <app-footer></app-footer>
  </v-app>
</template>

<script>
import Header from './components/Header.vue';
import Content from './components/Content.vue';
import Footer from './components/Footer.vue';

export default {
  name: 'app',
  components: {
    // 'app-header': Header,
    'app-content': Content,
    'app-footer': Footer
  },
  data() {
    return {
      sideNav: false
    }
  }
}
</script>

<style lang="sass">
</style>
