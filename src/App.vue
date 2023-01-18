<template>
  <v-app>
     <v-app-bar flat > 
      <div class="nav-bar">
        <div class="logo_holder">
          <v-btn class="lg_btn" text ><img class="logo" src="./assets/images/logo.svg" alt=""></v-btn>
        </div>
        <div class="menu_holder && hidden-md-and-down">
          <v-menu offset-y>
      <template v-slot:activator="{ on, attrs }">
        <v-btn
          color="gray"
          plain
          v-bind="attrs"
          v-on="on"
        >
          <span>Features</span> <v-icon small>mdi-chevron-down</v-icon>
        </v-btn>
      </template>
      <v-list>
        <v-list-item
          v-for="(item, index) in items"
          :key="index"
        >
          <v-list-item-title>{{ item.title }}</v-list-item-title>
        </v-list-item>
      </v-list>
    </v-menu>
    <v-menu offset-y>
      <template v-slot:activator="{ on, attrs }">
        <v-btn
          color="gray"
          plain
          v-bind="attrs"
          v-on="on"
        >
          <span>Company</span> <v-icon small>mdi-chevron-down</v-icon>
        </v-btn>
      </template>
      <v-list>
        <v-list-item
          v-for="(item, index) in items"
          :key="index"
        >
          <v-list-item-title>{{ item.title }}</v-list-item-title>
        </v-list-item>
      </v-list>
    </v-menu>

        </div>
        <div class="page_btns && hidden-md-and-down">
          <v-btn plain>Careers</v-btn>
          <v-btn plain>About</v-btn>
        </div>
        <v-spacer></v-spacer>
        <v-btn
          icon
          @click.stop="drawer = !drawer"
        >
        <v-icon>mdi-menu</v-icon>
        </v-btn>
        <div class="account_btns && hidden-md-and-down">
          <v-btn plain >Login</v-btn>
          <v-btn outlined >register</v-btn>
        </div>
      </div>
    </v-app-bar> 
    <v-navigation-drawer
      absolute
      v-model="drawer"
      temporary
      right
      class=" hidden-md-and-up"
    >
    <v-btn icon @click.stop="drawer = !drawer" ><v-icon large>mdi-close</v-icon></v-btn>
      <v-list dense>
        <v-list-group
          :value="true"
          no-action
          sub-group
        >
          <template v-slot:activator>
            <v-list-item-content>
              <v-list-item-title>Admin</v-list-item-title>
            </v-list-item-content>
          </template>

          <v-list-item
            v-for="([title, icon], i) in admins"
            :key="i"
            link
          >
            <v-list-item-title v-text="title"></v-list-item-title>

            <v-list-item-icon>
              <v-icon v-text="icon"></v-icon>
            </v-list-item-icon>
          </v-list-item>
        </v-list-group>
        <v-list-group
          :value="true"
          no-action
          sub-group
        >
          <template v-slot:activator>
            <v-list-item-content>
              <v-list-item-title>Admin</v-list-item-title>
            </v-list-item-content>
          </template>

          <v-list-item
            v-for="([title, icon], i) in admins"
            :key="i"
            link
          >
            <v-list-item-title v-text="title"></v-list-item-title>

            <v-list-item-icon>
              <v-icon v-text="icon"></v-icon>
            </v-list-item-icon>
          </v-list-item>
        </v-list-group>
        <v-list-item
         
        >
          <v-list-item-icon>
            <v-icon>mdi-basketball</v-icon>
          </v-list-item-icon>

          <v-list-item-content>
            <v-list-item-title> hada haka yji</v-list-item-title>
          </v-list-item-content>
        </v-list-item>
      </v-list>
      <div class="account_btns">
        <v-btn plain>Login</v-btn>
        <v-btn outlined>Register</v-btn>
      </div>
    </v-navigation-drawer>
    <v-main>
      <snap-challenge />
    </v-main>
  </v-app>
</template>

<script>
import SnapChallenge from "./components/snapChallenge.vue";

export default {
  name: "App",

  components: {
    SnapChallenge,
  },

  data: () => ({
    items: [
        { title: 'Click Me' },
        { title: 'Click Me' },
        { title: 'Click Me' },
        { title: 'Click Me 2' },
      ],
      navitems: [
          { title: 'Home', icon: 'mdi-home-city' },
          { title: 'My Account', icon: 'mdi-account' },
          { title: 'Users', icon: 'mdi-account-group-outline' },
        ],
        drawer: false,

        admins: [
        ['Management', 'mdi-account-multiple-outline'],
        ['Settings', 'mdi-cog-outline'],
      ],
      cruds: [
        ['Create', 'mdi-plus-outline'],
        ['Read', 'mdi-file-outline'],
        ['Update', 'mdi-update'],
        ['Delete', 'mdi-delete'],
      ],
      
  }),

  
};
</script>
<style lang="scss">
@import "./style/main.scss";
</style>
