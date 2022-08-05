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
            <v-list-item-content>Tartas {{ stats.cakes }}</v-list-item-content>
          </v-list-item>
          <v-list-item>
            <v-list-item-icon>
              <v-icon>mdi-comment</v-icon>
            </v-list-item-icon>
            <v-list-item-content
              >Comentarios {{ stats.comments }}</v-list-item-content
            >
          </v-list-item>
          <v-list-item>
            <v-list-item-icon>
              <v-icon>mdi-eye-settings</v-icon>
            </v-list-item-icon>
            <v-list-item-content>Vistas {{ stats.views }}</v-list-item-content>
          </v-list-item>
          <v-list-item>
            <v-list-item-icon>
              <v-icon>mdi-thumb-up</v-icon>
            </v-list-item-icon>
            <v-list-item-content>Likes {{ stats.likes }}</v-list-item-content>
          </v-list-item>
        </v-list>
      </v-card-text>
    </v-card>
  </div>
</template>

<script>
export default {
  data() {
    return {
      stats: {
        cakes: 0,
        comments: 0,
        views: 0,
        likes: 0,
      },
    }
  },

  async beforeMount() {
    await this.loadStats()
  },

  methods: {
    async loadStats() {
      try {
        const res = await fetch('http://localhost:4500/api/cake/stats')
        const data = await res.json()
        if (data.err) {
          console.log(data.err)
          return
        }
        this.stats = data
      } catch (err) {
        console.log(err)
      }
    },
  },
}
</script>

<style>
.barraTitulo {
  background-color: black;
  color: white;
}
.totalCard {
  border: solid black 4px;
}
</style>
