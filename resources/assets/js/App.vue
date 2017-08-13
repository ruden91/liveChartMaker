<template lang="html">
  <v-app>
    <v-navigation-drawer v-model="sideNav">
      <v-list>
        <v-list-tile v-for="item in menuItems" :key="item.title">
          <v-list-tile-action>
            <v-icon>{{item.icon}}</v-icon>
          </v-list-tile-action>
          <v-list-tile-content>
            {{item.title}}
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
        <v-btn flat v-for="item in menuItems" :key="item.title">
          <v-icon left dark>{{ item.icon }}</v-icon>
          {{ item.title }}
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
      sideNav: false,
      menuItems: [
        { icon: 'fa-users fa-2x', title: 'View Meetups' },
        { icon: 'fa-map-marker fa-2x', title: 'Organize Meetup' },
        { icon: 'fa-address-card fa-2x', title: 'Profile' },
        { icon: 'fa-user-circle fa-2x', title: 'Sign up' },
        { icon: 'fa-unlock-alt fa-2x', title: 'Sign in' }
      ]
    }
  }
}
</script>

<style lang="sass">
</style>
