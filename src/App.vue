<template>
  <v-app>
    <v-navigation-drawer
      v-model="drawer"
      :color="appColor"
      :expand-on-hover="$vuetify.breakpoint.lgAndDown"
      :mini-variant="$vuetify.breakpoint.lgAndDown"
      :permanent="$vuetify.breakpoint.mdAndUp"
      app
      dark
    >
      <SideMenu />
    </v-navigation-drawer>
    <v-app-bar :color="appColor" app dark>
      <v-app-bar-nav-icon
        v-if="$vuetify.breakpoint.smAndDown"
        @click="showDrawer"
      ></v-app-bar-nav-icon>
      <v-toolbar-title>Home</v-toolbar-title>
      <!--<HeaderMenu />-->
    </v-app-bar>
    <v-content>
      <router-view></router-view>
    </v-content>
  </v-app>
</template>

<script>
//import HeaderMenu from "@/components/organisms/HeaderMenu";
import SideMenu from "@/components/organisms/SideMenu";

export default {
  name: "App",
  components: {
    //HeaderMenu,
    SideMenu
  },
  data() {
    return {
      appColor: "blue darken-4",
      drawer: false
    };
  },
  methods: {
    showDrawer() {
      this.drawer = true;
    }
  }
};
</script>
