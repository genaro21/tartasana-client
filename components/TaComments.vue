<template>
  <div class="ta-comments">
    <TaCard title="Comentarios" icon="mdi-comment-account">
      <v-text-field
        v-model="title"
        placeholder="Título"
        outlined
      ></v-text-field>
      <v-textarea
        v-model="description"
        placeholder="Comentario"
        outlined
      ></v-textarea>
      <v-btn color="success" @click="onSubmit">Enviar</v-btn>
    </TaCard>
  </div>
</template>

<script>
export default {
  data() {
    return {
      title: '',
      description: '',
    }
  },
  methods: {
    async onSubmit() {
      try {
        const userId = localStorage.userId
        const cakeId = this.$route.params.id

        const body = JSON.stringify({
          title: this.title,
          description: this.description,
          userId,
          cakeId,
        })
        if (!this.title || !this.description) {
          alert('Debes rellenar todos los campos')
        }
        const res = await fetch('http://localhost:4500/api/comment/create', {
          method: 'post',
          headers: { 'Content-Type': 'application/json' },
          body,
        })
        const data = await res.json()
        if (data.err) {
          console.log(err)
        }
      } catch (err) {
        console.log(err)
      }
    },
  },
}
</script>
