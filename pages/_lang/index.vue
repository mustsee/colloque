<template xmlns:v-slot="http://www.w3.org/1999/XSL/Transform">
  <v-layout column justify-center align-center>
    <v-flex xs12>
      <v-flex xs12 md10 offset-md1>
        <v-card class="my-3 py-4" hover>
          <v-flex xs10 offset-xs1>
            <v-card-title class="display-2 pt-5 pb-3 justify-center">
              <div class="text-xs-center">
                {{ $t('index.title-1') }}
              </div>
              <div class="text-xs-center">
                {{ $t('index.title-2') }}
              </div>
            </v-card-title>
            <v-card-title class="display-1 pb-3 justify-center">
              <div class="text-xs-center" style="font-style: italic">
                {{ $t('index.title-3') }}
              </div>
            </v-card-title>
            <v-card-title class="headline pb-3 justify-center">
              <div class="text-xs-center">
                {{ $t('index.title-4') }}
              </div>
            </v-card-title>
          </v-flex>
          <v-flex xs12 sm10 offset-sm1 lg8 offset-lg2>
            <v-timeline class="my-5">
              <v-timeline-item
                v-for="item in $t('index.items')"
                :key="item.index"
                :color="`amber darken-${item.index}`"
                large
              >
                <template v-slot:opposite>
                  <span class="subheading"></span>
                </template>
                <v-card class="elevation-2">
                  <v-card-title class="headline" style="overflow: hidden">
                    {{ item.step }}
                  </v-card-title>
                  <v-card-text>
                    <div
                      v-for="text in item.texts"
                      :key="text"
                      class="text-xs-left pb-2"
                    >
                      {{ text }}
                    </div>
                  </v-card-text>
                </v-card>
              </v-timeline-item>
            </v-timeline>
          </v-flex>
          <v-card-text>
            <hr class="my-3" />
            <div class="subheading pa-5 text-xs-center">
              Contact : <a target="_blank">agnieszka.wiatrzyk@gmail.com</a>
            </div>
          </v-card-text>
        </v-card>
      </v-flex>
    </v-flex>
  </v-layout>
</template>

<script>
export default {
  head() {
    return { title: this.$t('index.title') }
  }
}
</script>
