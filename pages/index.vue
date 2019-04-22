<template xmlns:v-slot="http://www.w3.org/1999/XSL/Transform">
  <v-layout column justify-center align-center>
    <v-flex xs12>
      <v-flex xs12 md10 offset-md1>
        <v-card class="my-3 py-4" hover>
          <v-flex xs10 offset-xs1>
            <v-card-title class="display-2 pt-5 pb-3 justify-center">
              <div class="text-xs-center">
                « L’Esprit curieux. Collectionner en Europe
              </div>
              <div class="text-xs-center">
                (de Vasari à nos jours) »
              </div>
            </v-card-title>
            <v-card-title class="display-1 pb-3 justify-center">
              <div class="text-xs-center" style="font-style: italic">
                Colloque international organisé par la Bibliothèque Polonaise
              </div>
            </v-card-title>
            <v-card-title class="headline pb-3 justify-center">
              <div class="text-xs-center">
                Paris, les 24 et 25 octobre 2019
              </div>
            </v-card-title>
          </v-flex>
          <v-flex xs12 sm10 offset-sm1 lg8 offset-lg2>
            <v-timeline class="my-5">
              <v-timeline-item
                v-for="item in items"
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
  data() {
    return {
      items: [
        {
          index: 1,
          step: 'Organisation',
          texts: [
            `La Société Historique et Littéraire Polonaise
              (Bibliothèque Polonaise de Paris) en collaboration avec
              l’Académie Polonaise des Sciences de Paris.`,
            `Lieu : Bibliothèque Polonaise de Paris, 6 Quai d'Orléans,
              75004 Paris`
          ]
        },
        {
          index: 2,
          step: 'Objectif',
          texts: [
            `L'objectif du colloque est de réunir des représentants
          du milieu universitaire et muséal de trois pays différents (France, Italie,  Pologne) afin
          d'interroger la notion d'unité européenne à travers l'acte de
          collectionner, spécifique à la culture du Vieux Continent.`
          ]
        },
        {
          index: 3,
          step: 'Evènement',
          texts: [
            `Nous célébrerons le 70ème
anniversaire de la mort de Camille Gronkowski (1873-1949),
collectionneur majeur et bienfaiteur de la Bibliothèque Polonaise de Paris.`,
            `Ce sera l'occasion de présenter une exposition temporaire consacrée à la collection
de Camille Gronkowski qui fut l’un de premiers conservateurs du Petit Palais,`
          ]
        },
        {
          index: 4,
          step: 'Publications',
          texts: [
            `A l'issu du colloque, nous publierons les actes et nous rendrons
            disponible les vidéos enregistrées sur un site dédié.`
          ]
        }
      ]
    }
  }
}
</script>
