<template>
  <div class="ta-comment-item">
    <v-row>
      <v-col cols="4">
        <v-img :src="image" @click="onClick()"></v-img>
      </v-col>
      <v-col cols="8">
        <p class="font-weight-black">{{ email }}</p>
        <p>{{ comment }}</p>
      </v-col>
    </v-row>
  </div>
</template>

<script>
export default {
  props: {
    image: {
      type: String,
      required: true,
    },
    email: {
      type: String,
      required: true,
    },
    comment: {
      type: String,
      required: true,
    },
    cakeId: {
      type: String,
      required: true,
    },
  },
  methods: {
    onClick() {
      this.token = localStorage.token

      if (this.token) {
        this.$router.push(`/details/${cakeId}`)
      } else {
        alert(
          'Para poder acceder a fotos, comentarios, likes..., debes estar registrado'
        )
      }
    },
  },
}
</script>
