<template>
  <div class="ta-popular">
    <TaCard title="Las + populares" icon="mdi-heart-plus">
      <div class="ta-image-container">
        <v-row>
          <v-col
            cols="6"
            v-for="cake in cakes"
            :key="cake._id"
            class="ta-image-container-item"
          >
            <v-img :src="cake.image" @click="onClick(cake._id)"></v-img>
          </v-col>
        </v-row>
      </div>
    </TaCard>
  </div>
</template>

<script>
export default {
  data() {
    return {
      cakes: [],
    }
  },

  async beforeMount() {
    await this.loadMostPopular()
  },

  methods: {
    async loadMostPopular() {
      try {
        const res = await fetch('http://localhost:4500/api/cake/mostPopular')
        const data = await res.json()
        if (data.err) {
          console.log(data.err)
          return
        }
        this.cakes = []
        data.uploads.forEach((cake) => {
          this.cakes.push(cake)
        })
      } catch (err) {
        console.log(err)
      }
    },

    onClick(cakeId) {
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
