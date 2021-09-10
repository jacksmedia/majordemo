<template>
  <v-footer dark padless class="mt-5">
    <v-card
      flat
      tile
      class="primary white--text text-center align-self-md-stretch"
      width="100%"
    >
      <v-card-text>
        <v-btn v-for="(index, name, value) in myLinks" :key="index" class="mx-4 white--text" icon>
          <a :href="name">
          <v-icon size="3rem" class="white--text">{{ index }}</v-icon>
          </a>
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
        <h3 class="white--text" :style="{'text-shadow': '0px 4px 3px rgba(0,0,0,0.4), 0px 8px 13px rgba(0,0,0,0.1), 0px 18px 23px rgba(0,0,0,0.1)'}">
          Nothing on this page can be taken as Financial Advice.
        </h3>
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
    myLinks: {
      'https://www.linkedin.com/in/alexander-jacks/': 'fab fa-linkedin',
      'https://www.instagram.com/__j4cks__/': 'fab fa-instagram',
      'https://twitter.com/__j4cks__': 'fab fa-twitter'
    },
  })
};
</script>
