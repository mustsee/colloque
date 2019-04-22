<template>
  <v-app>
    <v-toolbar
      scroll-off-screen
      :scroll-threshold="400"
      fixed
      app
      flat
      style="border-bottom: 0.5px solid rgba(0,0,0,0.12)"
    >
      <v-toolbar-title :class="getToolbarTitleMargin">
        {{ title }}
      </v-toolbar-title>
      <v-divider vertical />
      <v-spacer></v-spacer>
      <v-divider vertical />
      <v-toolbar-items>
        <v-menu open-on-hover offset-y>
          <template v-slot:activator="{ on }">
            <div class="langButton px-3" v-on="on">
              <div class="subheading" style="font-family: arial">
                {{ $store.state.locale.toUpperCase() }}
              </div>
              <v-icon>arrow_drop_down</v-icon>
            </div>
          </template>
          <v-list>
            <v-list-tile v-for="(item, index) in items" :key="index">
              <v-list-tile-title>
                <NuxtLink
                  v-if="$i18n.locale === 'fr'"
                  :to="`/${item.lang}` + $route.fullPath"
                >
                  {{ item.lang.toUpperCase() }}
                </NuxtLink>
                <NuxtLink v-else :to="$route.fullPath.replace(/^\/[^\/]+/, '')">
                  {{ item.lang.toUpperCase() }}
                </NuxtLink>
              </v-list-tile-title>
            </v-list-tile>
          </v-list>
        </v-menu>
      </v-toolbar-items>
      <v-divider vertical />
    </v-toolbar>
    <v-content>
      <v-container fluid>
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
          lang: 'fr',
          to: '/'
        },
        {
          lang: 'en',
          to: '/en'
        }
      ],
      title: `L'Esprit curieux`
    }
  },
  computed: {
    getToolbarTitleMargin() {
      return this.$vuetify.breakpoint.mdAndUp ? 'pr-4' : 'pr-3'
    }
  }
}
</script>

<style>
.langButton {
  display: flex;
  align-items: center;
  cursor: pointer;
}
</style>
