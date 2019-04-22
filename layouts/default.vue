<template>
  <v-app>
    <v-toolbar fixed app>
      <v-toolbar-title :class="getToolbarTitleMargin">
        {{ title }}
      </v-toolbar-title>
      <v-divider vertical />
    </v-toolbar>
    <v-content>
      <v-container>
        <nuxt />
      </v-container>
    </v-content>
  </v-app>
</template>

<script>
export default {
  data() {
    return {
      items: [
        {
          icon: 'apps',
          title: 'Welcome',
          to: '/'
        },
        {
          icon: 'bubble_chart',
          title: 'Inspire',
          to: '/inspire'
        }
      ],
      title: `L'esprit curieux`
    }
  },
  computed: {
    getToolbarTitleMargin() {
      return this.$vuetify.breakpoint.mdAndUp ? 'pr-4' : 'pr-3'
    }
  }
}
</script>
