<template>
  <div class="ta-all-comments">
    <TaEmptyCard>
      <!-- <div class="ts-all-comments-container">
        <v-row v-for="(comment, index) in comments" :key="index">
          <v-col cols="4" class="d-flex justify-center">
            <v-avatar size="100">
              <v-img :src="comment.user.avatar"></v-img>
            </v-avatar>
          </v-col>
          <v-col cols="6">
            <b>{{ comment.title }}</b>
            <p>{{ comment.description }}</p>
          </v-col>
          <v-col cols="2">
            <v-btn color="warning">Delete</v-btn>
          </v-col>
          <v-col cols="12" v-if="index != comments.length - 1">
            <v-divider></v-divider>
          </v-col>
        </v-row>
      </div> -->
      <div class="ts-all-comments-container">
        <v-row v-for="(comment, index) in comments" :key="index">
          <v-col cols="4" class="d-flex justify-center">
            <v-avatar size="100">
              <v-img :src="comment.user.avatar"></v-img>
            </v-avatar>
          </v-col>
          <v-col cols="6">
            <b>{{ comment.title }}</b>
            <p>{{ comment.description }}</p>
          </v-col>
          <v-col cols="2" v-if="admin === 'true'">
            <v-btn color="warning" @click="() => delComment(comment)"
              >Delete</v-btn
            >
          </v-col>
          <v-col cols="12" v-if="index != comments.length - 1">
            <v-divider></v-divider>
          </v-col>
        </v-row>
      </div>
    </TaEmptyCard>
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
    comments: {
      type: Array,
      required: true,
    },
  },

  mounted() {
    this.admin = localStorage.admin
  },
  methods: {
    async delComment(comment) {
      console.log({ comment })
      try {
        const body = JSON.stringify({
          commentId: comment._id,
        })
        const res = await fetch('http://localhost:4500/api/comment/remove', {
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
      } catch (err) {
        console.log(err)
      }
    },
  },
}
</script>
