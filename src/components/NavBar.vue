<template>
    <v-toolbar flat dark color="#fe7b5f">
      <v-app-bar-nav-icon @click.stop="toggleSidebar()"></v-app-bar-nav-icon>
          <v-toolbar-title>Title</v-toolbar-title>

      <v-spacer></v-spacer>

      <v-btn icon>
        <v-icon>mdi-magnify</v-icon>
      </v-btn>

      <v-btn icon>
        <v-icon>mdi-heart</v-icon>
      </v-btn>

      <v-btn icon>
        <v-icon>mdi-dots-vertical</v-icon>
      </v-btn>
    </v-toolbar>

</template>

<script>
import { bus } from '../main'

export default {
  name:'NavBar',
      data () {
      return {
        items: [
          { title: 'Home', icon: 'mdi-view-dashboard', view: '/' },
          { title: 'About', icon: 'mdi-help-box', view: '/about' },
        ],
        right: null,
      }
    },
  methods: {
    toggleSidebar() {
      bus.$emit('toggleIt');
    }
  }
}
</script>
