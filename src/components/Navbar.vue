<template>
  <nav>
    <!-- topnav -->
    <v-app-bar
      app
      color="primary"
      dark
      src="https://cdn.vuetifyjs.com/images/backgrounds/bg-2.jpg"
    >
      <v-app-bar-nav-icon @click="drawer = !drawer"></v-app-bar-nav-icon>
      <img src="@/assets/logo.png" width="30px" class="mr-3" />
      <v-toolbar-title class="hidden-sm-and-down"
        >Vuetify Admin</v-toolbar-title
      >
      <v-spacer></v-spacer>
      <v-menu offset-y>
        <template v-slot:activator="{ on }">
          <v-btn text v-on="on">
            <span class="hidden-sm-and-down">Notification</span>
            <v-icon right>notifications_active</v-icon>
          </v-btn>
        </template>
        <v-list>
          <v-list-item
            v-for="(link, index) in menus"
            :key="index"
            @click="() => {}"
          >
            <v-list-item-title>{{ link.text }}</v-list-item-title>
          </v-list-item>
        </v-list>
      </v-menu>
      <v-btn text @click="logout()">
        <span class="hidden-sm-and-down">Exit</span>
        <v-icon right>exit_to_app</v-icon>
      </v-btn>
    </v-app-bar>

    <!-- sidenav -->
    <v-navigation-drawer
      v-model="drawer"
      dark
      app
      color="primary"
      src="https://cdn.vuetifyjs.com/images/backgrounds/bg-2.jpg"
    >
      <v-row>
        <v-col class="mt-2">
          <v-row justify="center">
            <v-avatar size="85" class="pa-0">
              <v-img src="@/assets/logo.png"></v-img>
            </v-avatar>
          </v-row>
        </v-col>
      </v-row>
      <v-row align="center" justify="center" class="white--text pa-0">
        <h3>
          Aji Pujo Hardiyanto
        </h3>
      </v-row>
      <v-row align="center" justify="center" class="white--text pa-0">
        <p>Superuser</p>
      </v-row>
      <v-divider class="mx-2"></v-divider>
      <v-list>
        <div v-for="(menu, index) in links" :key="index">
          <!-- if didnt have submenu -->
          <v-list-item router :to="menu.route" v-if="!menu.submenu">
            <v-list-item-action>
              <v-icon>{{ menu.icon }}</v-icon>
            </v-list-item-action>
            <v-list-item-content>
              <v-list-item-title>{{ menu.text }}</v-list-item-title>
            </v-list-item-content>
          </v-list-item>
          <!-- if have submenu -->
          <v-list-group v-if="menu.submenu">
            <template v-slot:activator>
              <v-list-item-action>
                <v-icon class="white--text">{{ menu.icon }}</v-icon>
              </v-list-item-action>
              <v-list-item-content>
                <v-list-item-title class="white--text">{{
                  menu.text
                }}</v-list-item-title>
              </v-list-item-content>
            </template>
            <div v-for="(submenu, index) in menu.submenu" :key="index">
              <v-list-item router :to="submenu.route" class="white--text">
                <v-list-item-action>
                  <v-icon class="ml-6">{{ submenu.icon }}</v-icon>
                </v-list-item-action>
                <v-list-item-content>
                  <v-list-item-title>{{ submenu.text }}</v-list-item-title>
                </v-list-item-content>
              </v-list-item>
            </div>
          </v-list-group>
        </div>
        <v-divider></v-divider>
        <v-list-item router to="/about">
          <v-list-item-action>
            <v-icon>person</v-icon>
          </v-list-item-action>
          <v-list-item-content>
            <v-list-item-title>About</v-list-item-title>
          </v-list-item-content>
        </v-list-item>
      </v-list>
    </v-navigation-drawer>
  </nav>
</template>

<script>
export default {
  data() {
    return {
      drawer: true,
      menus: [
        { text: "Message", route: "#" },
        { text: "Notification", route: "#" },
        { text: "Task", route: "#" },
        { text: "Job Desk", route: "#" },
      ],
      links: [
        {
          icon: "dashboard",
          text: "Dashboard",
          route: "/",
        },
        {
          icon: "library_books",
          text: "Basic UI",
          submenu: [
            {
              icon: "check_box",
              text: "Buttons",
              route: "/button",
            },
            {
              icon: "text_fields",
              text: "Typography",
              route: "/typography",
            },
          ],
        },
        {
          icon: "donut_small",
          text: "Icon",
          route: "/icon",
        },
        {
          icon: "description",
          text: "Form",
          route: "/form",
        },
        {
          icon: "table_chart",
          text: "Table",
          route: "/table",
        },
      ],
    };
  },
};
</script>
