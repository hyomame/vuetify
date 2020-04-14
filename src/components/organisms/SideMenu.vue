<template>
  <v-container class="pa-0">
    <v-list>
      <v-list-item>
        <v-list-item-icon>
          <v-icon>mdi-vuetify</v-icon>
        </v-list-item-icon>
        <v-list-item-title>title</v-list-item-title>
      </v-list-item>
      <v-divider></v-divider>
      <template v-for="(item, index) in menu">
        <v-list-item v-if="!item.list" :key="index">
          <v-list-item-icon>
            <v-icon>{{ item.icon }}</v-icon>
          </v-list-item-icon>
          <v-list-item-content>
            <v-list-item-title>{{ item.name }}</v-list-item-title>
          </v-list-item-content>
        </v-list-item>
        <v-list-group v-else :key="index" :prepend-icon="item.icon" no-action>
          <template #activator>
            <v-list-item-title>{{ item.name }}</v-list-item-title>
          </template>
          <v-list-item v-for="(submenu, index) in item.list" :key="index">
            <v-list-item-title>{{ submenu.name }}</v-list-item-title>
          </v-list-item>
        </v-list-group>
      </template>
    </v-list>
  </v-container>
</template>

<script>
export default {
  name: "SideMenu",
  data() {
    return {
      menu: [
        {
          name: "home",
          icon: "mdi-home"
        },
        {
          name: "setting",
          icon: "mdi-cog-outline",
          list: [
            {
              name: "name"
            },
            {
              name: "avatar"
            }
          ]
        },
        { name: "help", icon: "mdi-help" }
      ]
    };
  }
};
</script>
