<template>
  <div class="ta-all-comments">
    <TaEmptyCard>
      <div class="ts-all-comments-container">
        <v-row v-for="(comment, index) in comments" :key="comment.id">
          <v-col cols="4" class="d-flex justify-center">
            <v-avatar size="100">
              <v-img :src="comment.avatar"></v-img>
            </v-avatar>
          </v-col>
          <v-col cols="8">
            <b>{{ comment.title }}</b>
            <p>{{ comment.comment }}</p>
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
      comments: [
        {
          id: 1,
          email: 'pepe@gmail.com',
          title: 'Titulo 1',
          avatar: 'https://picsum.photos/536/354',
          comment: '-Comentario 1',
        },
        {
          id: 2,
          email: 'jose@gmail.com',
          title: 'Titulo 2',
          avatar: 'https://picsum.photos/id/237/536/354',
          comment: 'Comentario 2',
        },
        {
          id: 3,
          email: 'juan@gmail.com',
          title: 'Titulo 3',
          avatar: 'https://picsum.photos/seed/picsum/536/354',
          comment: 'Comentario 3',
        },
      ],
    }
  },
}
</script>
