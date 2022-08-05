<template>
  <div class="ta-lastest-comments">
    <TaCard title="Comentarios" icon="mdi-message-fast">
      <TaCommentItem
        v-for="comment in comments"
        :key="comment.comment._id"
        :image="comment.cake.image"
        :email="comment.user.email"
        :comment="comment.comment.description"
        :cakeId="comment.cake._id"
      />
    </TaCard>
  </div>
</template>

<script>
export default {
  data() {
    return {
      comments: [],
    }
  },

  async beforeMount() {
    await this.loadComments()
  },

  methods: {
    async loadComments() {
      try {
        const res = await fetch(
          'http://localhost:4500/api/comment/lastestComments'
        )
        const data = await res.json()
        if (data.err) {
          console.log(err)
          return
        }
        for (const comment of data.comments) {
          this.comments.push(comment)
        }
        console.log({ comments: this.comments })
      } catch (err) {
        console.log(err)
      }
    },
  },
}
</script>
