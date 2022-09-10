<template>
  <!-- <div class="ta-app-bar">
    <v-app-bar app color="rgb(200,200,200)">
      <v-toolbar-title>Las tartas de Ana María</v-toolbar-title>
      <v-spacer></v-spacer>
      <div v-if="!token">
        <v-btn text to="/sign-in">Sign In</v-btn>
        <v-btn text to="/sign-up">Sign Up</v-btn>
      </div>
      <div v-else class="d-flex justify-end">
        <v-avatar class="mt-2">
          <img :src="avatar" />
        </v-avatar>
        <p class="mt-5 mx-2 tituloBarra">{{ email }}</p>
        <v-btn text class="mx-16 my-4" @click="logout">Logout</v-btn>
      </div>
    </v-app-bar>
  </div> -->
  <v-card class="overflow-hidden">
    <v-app-bar
      absolute
      color="#6A76AB"
      dark
      shrink-on-scroll
      prominent
      src="https://picsum.photos/id/106/367/267"
      fade-img-on-scroll
      scroll-target="#scrolling-techniques-3"
    >
      <template v-slot:img="{ props }">
        <v-img
          v-bind="props"
          gradient="to top right, rgba(100,115,201,.7), rgba(25,32,72,.7)"
        ></v-img>
      </template>

      <v-app-bar-nav-icon></v-app-bar-nav-icon>

      <v-app-bar-title>Las tartas de Ana María</v-app-bar-title>

      <v-spacer></v-spacer>

      <v-btn icon>
        <v-icon>mdi-magnify</v-icon>
      </v-btn>

      <v-btn icon>
        <v-icon>mdi-heart</v-icon>
      </v-btn>

      <v-btn icon>
        <v-icon>mdi-dots-vertical</v-icon>
      </v-btn>

      <template v-slot:extension>
        <v-tabs align-with-title>
          <v-tab
            ><nuxt-link to="/home" class="tol-menu-link"
              >Inicio</nuxt-link
            ></v-tab
          >

          <v-tab>Sabores y raciones</v-tab>
          <v-tab>Quienes somos</v-tab>
          <v-tab>Contacto</v-tab>
          <v-tab
            ><nuxt-link to="" class="tol-menu-link"
              ><v-btn icon> <v-icon>mdi-facebook</v-icon> </v-btn>Facebook
            </nuxt-link></v-tab
          >
          <v-tab
            ><v-btn icon> <v-icon>mdi-instagram</v-icon> </v-btn
            >Instagram</v-tab
          >

          <v-tab v-show="admin === 'true'"
            ><nuxt-link to="/admin" class="tol-menu-link"
              >Admin</nuxt-link
            ></v-tab
          >
          <v-spacer></v-spacer>
          <div v-if="!token" class="mt-n1">
            <v-btn text to="/sign-in">Sign In</v-btn>
            <v-btn text to="/sign-up">Sign Up</v-btn>
          </div>
          <div v-else class="d-flex justify-end mt-n4">
            <v-avatar class="mt-2">
              <img :src="avatar" />
            </v-avatar>
            <p class="mt-5 mx-2 tituloBarra">{{ email }}</p>
            <v-btn text class="mx-16 my-4" @click="logout">Logout</v-btn>
          </div>
        </v-tabs>
      </template>
    </v-app-bar>
    <v-sheet
      id="scrolling-techniques-3"
      class="overflow-y-auto"
      max-height="600"
    >
      <v-container style="height: 225px"></v-container>
    </v-sheet>
  </v-card>
</template>

<script>
export default {
  data() {
    return {
      token: undefined,
      email: '',
      admin: '',
      avatar: undefined,
    }
  },
  beforeMount() {
    this.token = localStorage.getItem('token')
    this.email = localStorage.getItem('email')
    this.admin = localStorage.getItem('admin')
    this.avatar = localStorage.getItem('avatar')
  },
  mounted() {
    console.log(this.admin)
  },
  methods: {
    logout() {
      localStorage.clear()
      this.token = ''
      this.$router.push('/sign-in')
    },
  },
}
</script>

<style scoped>
.tituloBarra {
  font-size: 20px;
}
.v-app-bar-title_content {
  width: 100%;
}
.tol-menu-link {
  color: white;
  text-decoration: none;
}
</style>
