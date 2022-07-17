<template>
  <div class="ta-stats">
    <v-card>
      <v-card-title class="barraTitulo">
        <v-icon size="32" class="mx-2" style="color: white"
          >mdi-chart-box</v-icon
        >
        <p class="headline my-2">Stats</p>
      </v-card-title>
      <v-card-text class="totalCard">
        <v-list>
          <v-list-item>
            <v-list-item-icon>
              <v-icon>mdi-file-image</v-icon>
            </v-list-item-icon>
            <v-list-item-content>n# tartas</v-list-item-content>
          </v-list-item>
          <v-list-item>
            <v-list-item-icon>
              <v-icon>mdi-comment</v-icon>
            </v-list-item-icon>
            <v-list-item-content>n# comentarios</v-list-item-content>
          </v-list-item>
          <v-list-item>
            <v-list-item-icon>
              <v-icon>mdi-eye-settings</v-icon>
            </v-list-item-icon>
            <v-list-item-content>n# views</v-list-item-content>
          </v-list-item>
          <v-list-item>
            <v-list-item-icon>
              <v-icon>mdi-thumb-up</v-icon>
            </v-list-item-icon>
            <v-list-item-content>n# likes</v-list-item-content>
          </v-list-item>
        </v-list>
      </v-card-text>
    </v-card>
  </div>
</template>

<style>
.barraTitulo {
  background-color: black;
  color: white;
}
.totalCard {
  border: solid black 4px;
}
</style>
