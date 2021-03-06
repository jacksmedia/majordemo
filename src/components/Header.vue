<template>
  <nav>
    <v-toolbar
      color="primary overflow-hidden"
      :elevate-on-scroll="true"
      :hide-on-scroll="true"
      dark
    >
      <v-app-bar-nav-icon
        class="d-flex d-sm-none"
        @click="toggle"
      ></v-app-bar-nav-icon>
      <v-btn text large href="/">
        <g-image src="~/favicon.png" height="30" width="50" class="mr-3" />
        <span class="headline font-weight-bold"">{{
          $static.metadata.siteName
        }}</span>
      </v-btn>

      <v-spacer></v-spacer>
       <v-btn
        color="purple"
        elevation="2"
        @click="installer()"
        :style="{'display': installBtnStyle}">
          Install!
        </v-btn>
      <v-toolbar-items class="d-none d-sm-flex">
        <v-btn text to="/">Home</v-btn>
        <v-btn text to="/about">About</v-btn>
        <v-btn text to="/articles">Articles</v-btn>
      </v-toolbar-items>
    </v-toolbar>
    <v-navigation-drawer
      absolute
      v-model="collapse"
      :mini-variant.sync="mini"
      class="d-flex d-sm-none dark"
    >
      <v-list-item>
        <v-list-item-avatar>
          <g-image src="~/favicon.png"></g-image>
        </v-list-item-avatar>

        <v-btn icon @click.stop="mini = !mini">
          <v-icon>fa-chevron-left</v-icon>
        </v-btn>
      </v-list-item>

      <v-divider></v-divider>

      <v-list dense>
        <v-list-item
          v-for="item in items"
          :key="item.title"
          link
          :href="item.path"
        >
          <v-list-item-icon>
            <v-icon>{{ item.icon }}</v-icon>
          </v-list-item-icon>

          <v-list-item-content>
            <v-list-item-title>{{ item.title }}</v-list-item-title>
          </v-list-item-content>
        </v-list-item>
      </v-list>
    </v-navigation-drawer>
  </nav>
</template>

<static-query>
query {
  metadata {
    siteName
  }
}
</static-query>

<script>
export default {
  data() {
    return {
      collapse: false,
      items: [
        { title: "Home", icon: "fa-home", path: "/" },
        { title: "About", icon: "fa-user-astronaut", path: "/about" },
        { title: "Articles", icon: "fa-newspaper", path: "/articles" },
        { title: "Contact", icon: "fa-envelope", path: "/contact" }
      ],
      mini: false,
      installBtnStyle: "none",
      installer: undefined
    };
  },
  methods: {
    toggle() {
      this.collapse = !this.collapse;
    },
    created() {
      let installPrompt;

      window.addEventListener("beforeInstallPrompt", e => {
        // bugfix for Chrome 67 and earlier
        e.preventDefault();
        // save event for later triggering
        installPrompt = e;
        // update UI btn viz, for Add To Home Screen feature
        this.installBtnStyle = "block";
      });

      this.installer = () => {
        // hides UI btn
        this.installBtnStyle = "none";
        // show prompt
        installPrompt.prompt();
        // await user feedback
        installPrompt.userChoice.then(result => {
          if (result.outcome === "accepted") {
            console.log("User says YES");
          } else {
            console.log("User says NO");
          }
          installPrompt = null;
        });
      };
    }
  }
};
</script>
