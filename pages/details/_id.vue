<template>
  <div class="ta-details-id">
    <TaCakeDetails :cake="cake" />
    <TaComments />
    <TaAllComments />
  </div>
</template>

<script>
export default {
  async asyncData(ctx) {
    try {
      // -- VIEWS
      const body = JSON.stringify({
        cakeId: ctx.params.id,
      })
      const resView = await fetch('http://localhost:4500/api/cake/view', {
        method: 'post',
        headers: {
          'Content-Type': 'application/json',
        },
        body,
      })

      // -- load details
      const res = await fetch(
        `http://localhost:4500/api/cake/details/${ctx.params.id}`
      )
      const data = await res.json()

      const cake = data.cake
      const comments = data.comments

      return {
        cake,
        comments,
        onFetch: undefined,
      }
    } catch (err) {
      console.log(err)
      ctx.redirect('/home')
    }
  },

  mounted() {
    this.onFetch = setInterval(async () => {
      await this.loadDetails()
    }, 2000)
  },

  beforeDestroy() {
    clearInterval(this.onFetch)
  },

  methods: {
    async loadDetails() {
      try {
        const res = await fetch(
          `http://localhost:4500/api/cake/details/${this.cake._id}`
        )
        const data = await res.json()

        this.cake = data.cake
        this.comments = data.comments
      } catch (err) {
        console.log(err)
        this.$router.push('/home')
      }
    },
  },
}
</script>
