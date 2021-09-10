<template>
  <v-timeline :dense="$vuetify.breakpoint.smAndDown">
    <v-timeline-item :icon="'fa-star'" v-for="item in timeline" :key="item.event" >
       <span>{{item.event}}</span>
        <v-card class="elevation-4">
          <v-card-title class="px-5 primary white--text">{{item.caption}}</v-card-title>
          <v-card-text class="py-3 m-4">
            {{item.desc}}
          </v-card-text>
        </v-card>
      </v-timeline-item>
  </v-timeline>
</template>

<script>
export default {
  props: {
    timeline: Array    
  }
}
</script>