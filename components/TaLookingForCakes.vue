<template>
  <div class="ta-looking-for-cakes">
    <TaCard title="Búsqueda de tartas" icon="mdi-cake-layered">
      <div class="d-flex flex-wrap justify-space-between mt-4">
        <v-btn @click=";(todas = true), toda()">Todas</v-btn>
        <v-btn @click=";(categoria1 = true), cat1()">Categoría 1</v-btn>
        <v-btn @click=";(categoria2 = true), cat2()">Categoría 2</v-btn>
        <v-btn @click=";(categoria3 = true), cat3()">Categoría 3</v-btn>
        <v-btn @click=";(categoria4 = true), cat4()">Categoría 4</v-btn>

        <v-dialog v-model="todas" max-width="60%">
          <v-card>
            <v-card-title>Todas las tartas</v-card-title>
            <v-card-text>
              <v-row>
                <v-col cols="3" v-for="cake in cakes.data" :key="cake._id">
                  <v-img :src="cake.image" @click="onClick(cake._id)"></v-img>
                </v-col>
              </v-row>
            </v-card-text>
          </v-card>
        </v-dialog>

        <v-dialog v-model="categoria1" max-width="60%">
          <v-card>
            <v-card-title>Categoria 1</v-card-title>
            <v-card-text>
              <v-row>
                <v-col cols="3" v-for="cake in cakes1.data" :key="cake._id">
                  <v-img :src="cake.image" @click="onClick(cake._id)"></v-img>
                </v-col>
              </v-row>
            </v-card-text>
          </v-card>
        </v-dialog>

        <v-dialog v-model="categoria2" max-width="60%">
          <v-card>
            <v-card-title>Categoria 2</v-card-title>
            <v-card-text>
              <v-row>
                <v-col cols="3" v-for="cake in cakes2.data" :key="cake._id">
                  <v-img :src="cake.image" @click="onClick(cake._id)"></v-img>
                </v-col>
              </v-row>
            </v-card-text>
          </v-card>
        </v-dialog>

        <v-dialog v-model="categoria3" max-width="60%">
          <v-card>
            <v-card-title>Categoria 3</v-card-title>
            <v-card-text>
              <v-row>
                <v-col cols="3" v-for="cake in cakes3.data" :key="cake._id">
                  <v-img :src="cake.image" @click="onClick(cake._id)"></v-img>
                </v-col>
              </v-row>
            </v-card-text>
          </v-card>
        </v-dialog>

        <v-dialog v-model="categoria4" max-width="60%">
          <v-card>
            <v-card-title>Categoria 4</v-card-title>
            <v-card-text>
              <v-row>
                <v-col cols="3" v-for="cake in cakes4.data" :key="cake._id">
                  <v-img :src="cake.image" @click="onClick(cake._id)"></v-img>
                </v-col>
              </v-row>
            </v-card-text>
          </v-card>
        </v-dialog>
      </div>
    </TaCard>
  </div>
</template>

<script>
export default {
  data() {
    return {
      todas: false,
      categoria1: false,
      categoria2: false,
      categoria3: false,
      categoria4: false,
      cakes: [],
      cakes1: [],
      cakes2: [],
      cakes3: [],
      cakes4: [],
      category: '',
    }
  },
  methods: {
    async toda() {
      try {
        const res = await fetch('http://localhost:4500/api/cake/getAll')
        const data = await res.json()
        console.log({ data })
        if (data.err) {
          alert(data.err)
          return
        }

        this.cakes = data
      } catch (err) {
        console.log(err)
      }
    },

    async cat1() {
      try {
        const res = await fetch(
          'http://localhost:4500/api/cake/getCategory/Categoría 1'
        )
        const data = await res.json()
        console.log({ data })
        if (data.err) {
          alert(data.err)
          return
        }
        this.cakes1 = data
      } catch (err) {
        console.log(err)
      }
    },
    async cat2() {
      try {
        const res = await fetch(
          'http://localhost:4500/api/cake/getCategory/Categoría 2'
        )
        const data = await res.json()
        console.log({ data })
        if (data.err) {
          alert(data.err)
          return
        }
        this.cakes2 = data
      } catch (err) {
        console.log(err)
      }
    },
    async cat3() {
      try {
        const res = await fetch(
          'http://localhost:4500/api/cake/getCategory/Categoría 3'
        )
        const data = await res.json()
        console.log({ data })
        if (data.err) {
          alert(data.err)
          return
        }
        this.cakes3 = data
      } catch (err) {
        console.log(err)
      }
    },
    async cat4() {
      try {
        const res = await fetch(
          'http://localhost:4500/api/cake/getCategory/Categoría 4'
        )
        const data = await res.json()
        console.log({ data })
        if (data.err) {
          alert(data.err)
          return
        }
        this.cakes4 = data
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
