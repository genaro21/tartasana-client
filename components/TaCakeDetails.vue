<template>
  <div class="ta-cake-details">
    <TaCard2 :title="cake.title" icon="mdi-heart">
      <div class="ta-image-details-container">
        <v-img height="400px" contain :src="cake.image" />
        <div class="ta-image-details-container-description mt-4">
          <p class="headline font-weight-black">{{ cake.title }}</p>
          <p>{{ cake.description }}</p>
        </div>
        <!-- <div class="ta-image-details-container-icon d-flex">
          <div class="d-flex justify-start">
            <v-btn color="success" @click="onLike">
              <v-icon class="mr-2">mdi-thumb-up</v-icon>
              Like
            </v-btn>
            <div class="mx-12">
              <v-icon class="d-flex justify-center">mdi-cards-heart</v-icon>
              <p>Likes {{ cake.likes }}</p>
            </div>
            <div class="mx-12">
              <v-icon class="d-flex justify-center">mdi-eye-settings</v-icon>
              <p>Views {{ cake.views }}</p>
            </div>
          </div>
          <v-spacer></v-spacer>
          <v-btn color="warning" class="mx-8" @click="delCake">Delete</v-btn>
        </div> -->
        <div
          v-if="admin === 'true'"
          class="ta-image-details-container-icon d-flex"
        >
          <div class="d-flex justify-start">
            <v-btn color="success" @click="onLike">
              <v-icon class="mr-2">mdi-thumb-up</v-icon>
              Like
            </v-btn>
            <div class="mx-12">
              <v-icon class="d-flex justify-center">mdi-cards-heart</v-icon>
              <p>Likes {{ cake.likes }}</p>
            </div>
            <div class="mx-12">
              <v-icon class="d-flex justify-center">mdi-eye-settings</v-icon>
              <p>Views {{ cake.views }}</p>
            </div>
          </div>
          <v-spacer></v-spacer>
          <v-btn color="warning" class="mx-8" @click="delCake">Delete</v-btn>
        </div>

        <div v-else class="ta-image-details-container-icon d-flex">
          <div class="d-flex justify-start">
            <v-btn color="success" @click="onLike">
              <v-icon class="mr-2">mdi-thumb-up</v-icon>
              Like
            </v-btn>
            <div class="mx-12">
              <v-icon class="d-flex justify-center">mdi-cards-heart</v-icon>
              <p>Likes {{ cake.likes }}</p>
            </div>
            <div class="mx-12">
              <v-icon class="d-flex justify-center">mdi-eye-settings</v-icon>
              <p>Views {{ cake.views }}</p>
              <p></p>
            </div>
          </div>
        </div>
      </div>
    </TaCard2>
  </div>
</template>

<script>
export default {
  data() {
    return {
      admin: undefined,
    }
  },
  props: {
    cake: {
      type: Object,
      required: true,
    },
  },
  mounted() {
    this.admin = localStorage.admin
  },
  methods: {
    async onLike() {
      try {
        const body = JSON.stringify({
          cakeId: this.cake._id,
        })
        const res = await fetch('http://localhost:4500/api/cake/like', {
          method: 'post',
          headers: {
            'Content-Type': 'application/json',
          },
          body,
        })

        const data = res.json()
        if (data.err) {
          console.log(err)
        }
      } catch (err) {
        console.log(err)
      }
    },
    async delCake() {
      console.log({ cakeId: this.cake._id })

      try {
        const body = JSON.stringify({
          cakeId: this.cake._id,
        })
        const res = await fetch('http://localhost:4500/api/cake/remove', {
          method: 'delete',
          headers: {
            'Content-Type': 'application/json',
          },
          body,
        })
        const data = await res.json()
        console.log({ data })
        if (data.err) {
          console.log(err)
        }
        this.$router.replace('/home')
      } catch (err) {
        console.log(err)
      }
    },
  },
}
</script>
