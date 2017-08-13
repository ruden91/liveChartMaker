<template lang="html">
  <v-app>
    <v-navigation-drawer v-model="sideNav">
      <v-list>
        <v-list-tile
          v-for="item in menuItems"
          :key="item.title"
          router
          :to="item.link"
        >
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
      <v-toolbar-title>
        <router-link to="/" tag="span" style="cursor:pointer">Webruden</router-link>
      </v-toolbar-title>
      <v-spacer></v-spacer>
      <v-toolbar-items class="hidden-xs-only">
        <v-btn
          flat
          v-for="item in menuItems" 
          :key="item.title"
          router
          :to="item.link"
        >
          <v-icon left dark>{{ item.icon }}</v-icon>
          {{ item.title }}
        </v-btn>
      </v-toolbar-items>
    </v-toolbar>
    <main>
      <router-view></router-view>
    </main>
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
        { icon: 'fa-users fa-2x', title: 'View Meetups', link: '/meetups' },
        { icon: 'fa-map-marker fa-2x', title: 'Organize Meetup', link: '/meetups/new' },
        { icon: 'fa-address-card fa-2x', title: 'Profile', link: '/profile' },
        { icon: 'fa-user-circle fa-2x', title: 'Sign up', link: '/signup' },
        { icon: 'fa-unlock-alt fa-2x', title: 'Sign in', link: '/signin' }
      ]
    }
  }
}
</script>

<style lang="sass">
</style>
