<template>
  <div class="ta-sign-in-form">
    <v-row>
      <v-col cols="3"></v-col>
      <v-col cols="6">
        <v-card class="mt-4">
          <v-card-title class="d-flex justify-center">Sign In</v-card-title>
          <v-card-text>
            <v-text-field placeholder="Email" outlined></v-text-field>
            <v-text-field
              placeholder="Passsword"
              type="password"
              outlined
            ></v-text-field>
            <v-btn color="success" block>Enviar</v-btn>
          </v-card-text>
        </v-card>
      </v-col>
      <v-col cols="3"></v-col>
    </v-row>
  </div>
</template>
