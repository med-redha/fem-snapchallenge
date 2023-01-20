<template>
  <v-app>
    <v-app-bar flat>
      <div class="nav-bar">
        <div class="logo_holder">
          <v-btn class="lg_btn" text
            ><img class="logo" src="./assets/images/logo.svg" alt=""
          /></v-btn>
        </div>
        <div class="menu_holder && hidden-md-and-down">
          <v-menu offset-y rounded="24px" min-width="200px"  >
            <template v-slot:activator="{ on, attrs }">
              <v-btn color="gray" plain v-bind="attrs" v-on="on">
                <span>Features</span> <v-icon small>mdi-chevron-down</v-icon>
              </v-btn>
            </template>
            <v-list class="ml-8">
              <v-list-item v-for="(item, index) in items" :key="index">
                <v-list-item-title> <v-icon small class="mr-4">{{ item.icon }}</v-icon>{{ item.title }}</v-list-item-title>
              </v-list-item>
            </v-list>
          </v-menu>
          <v-menu offset-y rounded="18px" min-width="150px" max-height="160px">
            <template v-slot:activator="{ on, attrs }">
              <v-btn color="gray" plain v-bind="attrs" v-on="on">
                <span>Company</span> <v-icon small>mdi-chevron-down</v-icon>
              </v-btn>
            </template>
            <v-list class="ml-8">
              <v-list-item v-for="(item, index) in itemes" :key="index">
                <v-list-item-title>    {{ item.title }}</v-list-item-title>
              </v-list-item>
            </v-list>
          </v-menu>
        </div>
        <div class="page_btns && hidden-md-and-down">
          <v-btn plain>Careers</v-btn>
          <v-btn plain>About</v-btn>
        </div>
        <v-spacer></v-spacer>
        <v-btn icon @click.stop="drawer = !drawer" class="d-lg-none .d-xl-flex">
          <v-icon>mdi-menu</v-icon>
        </v-btn>
        <div class="account_btns && hidden-md-and-down">
          <v-btn plain>Login</v-btn>
          <v-btn outlined>register</v-btn>
        </div>
      </div>
    </v-app-bar>
    <v-navigation-drawer
      absolute
      v-model="drawer"
      temporary
      right
      class="hidden-md-and-up "
    >
      <v-list dense>
        
            <div class="close_draw">
        <v-btn icon @click.stop="drawer = !drawer"
        ><v-icon large>mdi-close</v-icon></v-btn
      >
    </div>
          
        <v-list-group :value="true" no-action sub-group >
 
          <template v-slot:activator  >
            <v-list-item-content>
              <v-list-item-title>Features</v-list-item-title>
            </v-list-item-content>
          </template>

          <v-list-item v-for="([title, icon], i) in features" :key="i" link>
            <v-list-item-icon>
              <v-icon v-text="icon"></v-icon>
            </v-list-item-icon>
            <v-list-item-title v-text="title"></v-list-item-title>
          </v-list-item>
        </v-list-group>
        <v-list-group :value="true" no-action sub-group>
          <template v-slot:activator>
            <v-list-item-content>
              <v-list-item-title>Company</v-list-item-title>
            </v-list-item-content>
          </template>

          <v-list-item v-for="([title], i) in company" :key="i" link>
            
            <v-list-item-title v-text="title"></v-list-item-title>
          </v-list-item>
        </v-list-group>
        
        <v-list-item class="ml-5">
          <v-list-item-content>
            <v-list-item-title> About</v-list-item-title>
          </v-list-item-content>
        </v-list-item>
        <v-list-item>
          <v-list-item-content class="ml-5">
            <v-list-item-title> Careers</v-list-item-title>
          </v-list-item-content>
        </v-list-item>
      </v-list>
      
      <div class="accounted_btns">
        <v-btn plain>Login</v-btn>
        <v-btn outlined width="150px" height="58" class="reg_btn">Register</v-btn>
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
      { title: "Todo List", icon: "mdi-notebook-outline" },
      { title: "Calander", icon: "mdi-calendar-plus" },
      { title: "Reminders", icon: "mdi-bell" },
      { title: "Planning", icon: "mdi-clock" },
    ],
    itemes: [
      { title: "History"  },
      { title: "About"  },
      { title: "Blog"  },
    ],
    drawer: false,

    features: [
      ["Todo List", "mdi-notebook-outline"],
      ["Calander", "mdi-calendar-plus"],
      ["Reminders", "mdi-bell"],
      ["Planning", "mdi-clock"],
    ],
    company: [
      ["History"],
      ["About" ],
      ["Blog" ],
    ],
    cruds: [
      ["Create", "mdi-plus-outline"],
      ["Read", "mdi-file-outline"],
      ["Update", "mdi-update"],
      ["Delete", "mdi-delete"],
    ],
  }),
};
</script>
<style lang="scss">
@import "./style/main.scss";
</style>
