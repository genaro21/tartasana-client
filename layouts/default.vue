<template>
  <div class="ta-layout-default">
    <v-app>
      <TaAppBar />
      <v-container class="my-16">
        <v-row>
          <v-col cols="9">
            <Nuxt />
          </v-col>
          <v-col cols="3">
            <TaPopular />
            <TaLastestComments />
            <!-- <TaTradicional /> -->
            <TaStats />
          </v-col>
        </v-row>
      </v-container>
    </v-app>
  </div>
</template>
