<template>
  <div class="ta-upload-cake">
    <TaCard title="Crear tarta" icon="mdi-cake-layered">
      <v-row>
        <v-col cols="3"></v-col>
        <v-col cols="6">
          <div class="ta-upload-cake mt-10">
            <v-file-input
              prepend-icon=""
              outlined
              placeholder="Archivo imagen"
              name="image"
              v-model="image"
              required
            ></v-file-input>
            <v-text-field
              outlined
              placeholder="Titulo"
              name="title"
              v-model="title"
              required
            ></v-text-field>
            <v-select
              :items="items"
              label="Categoría"
              outlined
              v-model="category"
              required
            ></v-select>

            <v-textarea
              outlined
              placeholder="Descripción"
              name="description"
              v-model="description"
              required
            ></v-textarea>
            <div class="ta-btn-container d-flex justify-end mr-4">
              <v-btn color="success" @click="submit">Enviar</v-btn>
            </div>
          </div>
        </v-col>
        <v-col cols="3"></v-col>
      </v-row>
    </TaCard>
  </div>
</template>

<script>
export default {
  data() {
    return {
      image: undefined,
      title: '',
      category: '',
      description: '',
      items: ['Categoría 1', 'Categoría 2', 'Categoría 3', 'Categoría 4'],
    }
  },
  methods: {
    async submit() {
      console.log(this.title)
      const formData = new FormData()

      formData.enctype = 'multipart/form-data'
      formData.append('image', this.image)
      formData.append('title', this.title)
      formData.append('category', this.category)
      formData.append('description', this.description)

      console.log(this.image, this.title, this.category, this.description)
      if (!this.title || !this.category || !this.description) {
        return alert(
          'Ana María, haz el favor de rellenar todos los campos, para poder guardar tu maravillosa tarta ;))'
        )
      }

      try {
        const res = await fetch('http://localhost:4500/api/cake/upload', {
          method: 'POST',
          body: formData,
        })
        const data = await res.json()
        if (data.err) {
          alert(data.err)
        } else {
          this.$router.push('/home')
        }
      } catch (err) {
        alert(err.message)
      }
    },
  },
}
</script>
