<template>
  <div class="ta-upload-cake">
    <TaCard title="Crear tarta" icon="mdi-cake-layered">
      <div class="ta-upload-cake">
        <v-form class="my-14">
          <v-file-input
            prepend-icon=""
            outlined
            placeholder="Archivo imagen"
            name="file"
          ></v-file-input>
          <v-text-field
            outlined
            placeholder="Titulo"
            name="title"
          ></v-text-field>
          <v-select :items="items" label="Categoría" outlined></v-select>
          <!-- <v-text-field
            outlined
            placeholder="Categoría"
            name="category"
          ></v-text-field> -->
          <v-textarea
            outlined
            placeholder="Descripción"
            name="description"
          ></v-textarea>
          <div class="ta-btn-container d-flex justify-end mr-4">
            <v-btn color="success">Enviar</v-btn>
          </div>
        </v-form>
      </div>
    </TaCard>
  </div>
</template>

<script>
export default {
  data: () => ({
    items: ['Categoría 1', 'Categoría 2', 'Categoría 3', 'Categoría 4'],
  }),
}
</script>
