<template>
  <div class="ta-app-bar">
    <v-app-bar app color="pink">
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
  </div>
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
</style>
