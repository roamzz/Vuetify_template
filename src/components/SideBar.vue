<template>
  <v-navigation-drawer left app v-model="drawer">
    <v-list-item>
      <v-list-item-content>
        <v-list-item-title class="title">
          my App
        </v-list-item-title>
        <v-list-item-subtitle>
          sub
        </v-list-item-subtitle>
      </v-list-item-content>
    </v-list-item>

    <v-divider></v-divider>

    <v-list dense nav>
      <v-list-item v-for="item in items" :key="item.title" :to="item.view">
        <v-list-item-icon>
          <v-icon>{{ item.icon }}</v-icon>
        </v-list-item-icon>

        <v-list-item-content>
          <v-list-item-title>{{ item.title }}</v-list-item-title>
        </v-list-item-content>
      </v-list-item>
    </v-list>
    <template v-slot:append>
      <div class="pa-2">
        <v-btn block>
          Logout
        </v-btn>
      </div>
    </template>
  </v-navigation-drawer>
</template>
<script>
import { bus } from "../main";

export default {
  data() {
    return {
      drawer: true,
      items: [
        { title: "Home", icon: "mdi-view-dashboard", view: "/" },
        { title: "About", icon: "mdi-help-box", view: "/about" }
      ]
    };
  },
  computed: {
    mini() {
      return this.$vuetify.breakpoint.mdAndDown;
    }
  },
  created() {
    bus.$on("toggleIt", data => {
      console.log(data);

      this.drawer = !this.drawer;
    });
  }
};
</script>