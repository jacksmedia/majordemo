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
        <a class="white--text" href="https://alexanderjacks.info" target="_blank"
          >Alexander Jacks</a
        >
        <br/>
        <v-icon class="white--text">fa-laptop-code</v-icon> & <v-icon class="white--text">fa-camera</v-icon>
        
        
      </v-card-text>

      <v-divider></v-divider>

      <v-card-text class="white--text">
        {{ new Date().getFullYear() }} — 
        <strong>
          <a class="white--text" href="https://jacks.media" target="_blank">
            Jacks Media
          </a>
        </strong>
      </v-card-text>
    </v-card>
  </v-footer>
</template>

<script>
export default {
  components: {},
  data: () => ({
    icons: [
      "fab fa-facebook",
      "fab fa-twitter",
      "fab fa-linkedin",
      "fab fa-instagram"
    ]
  })
};
</script>
