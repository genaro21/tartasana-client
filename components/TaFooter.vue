<template>
  <v-footer class="tol-footer" color="#FFC4C4" padless>
    <v-row justify="center" no-gutters>
      <v-btn
        v-for="link in links"
        :key="link.title"
        color="white"
        text
        rounded
        class="my-2"
        @click="() => onClick(link.value)"
      >
        {{ link.title }}
      </v-btn>
      <v-col cols="12" class="pink lighten-2 py-4 text-center white--text">
        {{ new Date().getFullYear() }} — <strong>d´Lucas</strong>
      </v-col>
    </v-row>
  </v-footer>
</template>
<script>
export default {
  data: () => ({
    links: [
      {
        title: 'Inicio',
        value: '/home',
      },
      {
        title: 'Sabores y raciones',
        value: '/aceitunas',
      },
      {
        title: 'Quienes somos',
        value: '/frutoseco',
      },
      {
        title: 'Contacto',
        value: '/caramelos',
      },
      {
        title: 'Facebook',
        value: '/carrito',
      },

      {
        title: 'Instagram',
        value: '/signIn',
      },
      {
        title: 'Registrarse',
        value: '/sign-up',
      },
    ],
  }),
  methods: {
    onClick(path) {
      this.$router.push(path)
    },
  },
}
</script>
<style scoped>
.color-footer {
  background-color: black;
}
</style>
