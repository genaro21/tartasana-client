<template>
  <div class="ta-recent-uploads">
    <TaCard title="Ultimas entradas" icon="mdi-fast-forward">
      <div class="ta-image-container">
        <v-row>
          <v-col
            cols="3"
            v-for="cake in cakes"
            :key="cake._id"
            class="ta-image-container-item"
          >
            <v-card @click="onClick(cake._id)">
              <v-card-text>
                <v-img :src="cake.image"></v-img>
              </v-card-text>
            </v-card>
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

  async mounted() {
    await this.loadCake()
  },

  methods: {
    async loadCake() {
      try {
        const res = await fetch('http://localhost:4500/api/cake/recentUpload')
        const data = await res.json()
        if (data.err) {
          alert(data.err)
          return
        }
        for (const cake of data.uploads) {
          this.cakes.push(cake)
        }
        console.log('cake: ', cake)
      } catch (err) {
        // AQUI DA UN ERROR Y NO SE CUAL
        alert(err.message)
      }
    },
    onClick(cakeId) {
      console.log(cakeId)
      this.$router.push(`/details/${cakeId}`)
    },
  },
}
</script>
