<template>
  <div class="ta-sign-up-form">
    <v-row>
      <v-col cols="3"></v-col>
      <v-col cols="6">
        <v-card>
          <v-card-title class="d-flex justify-center">Sign Up</v-card-title>
          <v-card-text>
            <v-file-input
              placeholder="Introduce tu foto"
              prepend-icon=""
              outlined
            ></v-file-input>
            <v-text-field placeholder="Nombre" outlined></v-text-field>
            <v-text-field placeholder="Apellidos" outlined></v-text-field>
            <v-text-field placeholder="Teléfono" outlined></v-text-field>
            <v-text-field placeholder="Email" outlined></v-text-field>
            <v-text-field placeholder="Contraseña" outlined></v-text-field>
            <v-text-field
              placeholder="Repite contraseña"
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
