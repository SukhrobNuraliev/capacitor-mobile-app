<template>
  <v-app dark>
    <v-navigation-drawer
      v-model="drawer"
      :mini-variant="miniVariant"
      :clipped="clipped"
      fixed
      app
    >
      <v-list>
        <v-list-item
          v-for="(item, i) in items"
          :key="i"
          :to="item.to"
          router
          exact
        >
          <v-list-item-action>
            <v-icon>{{ item.icon }}</v-icon>
          </v-list-item-action>
          <v-list-item-content>
            <v-list-item-title v-text="item.title" />
          </v-list-item-content>
        </v-list-item>
      </v-list>
    </v-navigation-drawer>
    <v-app-bar :clipped-left="clipped" fixed app>
      <v-app-bar-nav-icon @click.stop="drawer = !drawer" />
      <v-btn icon @click.stop="miniVariant = !miniVariant">
        <v-icon>mdi-{{ `chevron-${miniVariant ? "right" : "left"}` }}</v-icon>
      </v-btn>
      <v-toolbar-title v-text="title" />
      <v-spacer />
      <v-btn icon @click.stop="rightDrawer = !rightDrawer">
        <v-icon>mdi-menu</v-icon>
      </v-btn>
    </v-app-bar>
    <v-main>
      <v-container>
        <Nuxt />
      </v-container>
    </v-main>
    <v-bottom-navigation
      fixed
      grow
      v-model="value"
      :input-value="active"
      color="blue lighten-5"
    >
      <v-btn to="/cards">
        <span>Cards</span>

        <v-icon>mdi-card-account-details</v-icon>
      </v-btn>

      <v-btn to="/">
        <span>Home</span>

        <v-icon>mdi-home</v-icon>
      </v-btn>

      <v-btn to="/forms">
        <span>Form</span>

        <v-icon>mdi-book-information-variant</v-icon>
      </v-btn>
    </v-bottom-navigation>
    <v-navigation-drawer v-model="rightDrawer" :right="right" temporary fixed>
      <v-list class="mx-3">
        <v-alert
          v-model="alert"
          dismissible
          color="blue lighten-1"
          border="left"
          elevation="2"
          colored-border
          icon="mdi-telegram"
        >
          Telegram got <strong>5</strong> new timeline!.
        </v-alert>
        <v-alert
          v-model="alert"
          dismissible
          color="cyan"
          border="left"
          elevation="2"
          colored-border
          icon="mdi-twitter"
        >
          You've got <strong>5</strong> new timeline!.
        </v-alert>
        <v-alert
          v-model="alert"
          dismissible
          color="red"
          border="left"
          elevation="2"
          colored-border
          icon="mdi-instagram"
        >
          Instagram <strong>5</strong> new!.
        </v-alert>
        <v-alert dense text type="success">
          I'm a alert with <strong>text</strong>
        </v-alert>
        <v-alert icon="mdi-shield-lock-outline" prominent text type="info">
          Donec quam, acus.
        </v-alert>
        <v-alert color="blue-grey" dark dense icon="mdi-school" prominent>
          Sed augue ipsum,
        </v-alert>
        <v-alert prominent type="error">
          <v-row align="center">
            <v-col class="grow"> Nunc nonummy </v-col>
            <v-col class="shrink pt-0">
              <v-btn>Take action</v-btn>
            </v-col>
          </v-row>
        </v-alert>
      </v-list>
    </v-navigation-drawer>
  </v-app>
</template>

<script>
export default {
  data() {
    return {
      clipped: false,
      drawer: false,
      fixed: false,
      items: [
        {
          icon: "mdi-apps",
          title: "Home",
          to: "/",
        },
        {
          icon: "mdi-card-account-details",
          title: "Cards",
          to: "/cards",
        },
        {
          icon: "mdi-book-information-variant",
          title: "Form",
          to: "/forms",
        },
      ],
      miniVariant: false,
      right: true,
      rightDrawer: false,
      title: "Conda Mobile",
    };
  },
};
</script>
