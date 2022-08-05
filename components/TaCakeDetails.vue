<template>
  <div class="ta-cake-details">
    <TaCard2 :title="cake.title" icon="mdi-heath">
      <div class="ta-image-details-container">
        <v-img height="400px" :src="cake.image" />
        <div class="ta-image-details-container-description mt-4">
          <p class="headline font-weight-black">{{ cake.title }}</p>
          <p>{{ cake.description }}</p>
        </div>
        <div class="ta-image-details-container-icon d-flex">
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
          <div class="mr-6 my-2"><p>12/05/2021</p></div>
        </div>
      </div>
    </TaCard2>
  </div>
</template>

<script>
export default {
  props: {
    cake: {
      type: Object,
      required: true,
    },
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
  },
}
</script>
