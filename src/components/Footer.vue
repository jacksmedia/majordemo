<template>
  <v-footer dark padless class="mt-5">
    <v-card
      flat
      tile
      class="primary white--text text-center align-self-md-stretch"
      width="100%"
    >
      <v-card-text>
        <v-btn v-for="icon in icons" :key="icon" class="mx-4 white--text" icon>
          <v-icon size="24px">{{ icon }}</v-icon>
        </v-btn>
      </v-card-text>

      <v-card-text class="white--text pt-0">
        All <v-icon class="white--text">fa-laptop-code</v-icon> & <v-icon class="white--text">fa-camera</v-icon> 
        <br/>
        <a class="white--text" href="https://j4cks.com" target="_blank"
          >Alexander Jacks</a
        >
      </v-card-text>

      <v-divider></v-divider>
        <h1 class="white--text" :style="{'text-shadow': '0px 4px 3px rgba(0,0,0,0.4), 0px 8px 13px rgba(0,0,0,0.1), 0px 18px 23px rgba(0,0,0,0.1)'}">
          Nothing on this page can be taken as Financial Advice.
        </h1>
      <v-divider></v-divider>

      <v-card-text class="flex-column justify-center align-center">
        <div class="white--text">
          {{ new Date().getFullYear() }}
        </div>
        <div>
          <a href="https://jacks.media" target="_blank">
            <g-image src="~/favicon.png" height="35" width="50" class="mr-5" />
          </a>
        </div>
        <div>
          <a class="white--text" href="https://jacks.media" target="_blank">
            Jacks Media
          </a>
        </div>
      </v-card-text>
    </v-card>
  </v-footer>
</template>

<script>
export default {
  components: {},
  data: () => ({
    icons: [
      "fab fa-linkedin",
      "fab fa-instagram",
      "fab fa-twitter"
    ],
    sociallinks: [
      "https://www.facebook.com/alexanderd.jacks/",
      "https://www.instagram.com/__j4cks__/",
      "https://twitter.com/__j4cks__/"
    ]
  })
};
</script>
