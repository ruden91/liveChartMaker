<template lang="html">
    <v-toolbar>
      <v-toolbar-side-icon></v-toolbar-side-icon>
      <v-toolbar-title>Webruden</v-toolbar-title>
      <v-spacer></v-spacer>
      <v-toolbar-items>
        <v-btn flat>
          {{ sideNav }}
        </v-btn>
      </v-toolbar-items>
    </v-toolbar>

</template>

<script>
export default {
  props:['sideNav']
}
</script>

<style lang="css">
</style>
