<template>
  <div class="ta-sign-in-form">
    <v-row>
      <v-col cols="3"></v-col>
      <v-col cols="6">
        <v-card class="mt-4">
          <v-card-title class="d-flex justify-center">Sign In</v-card-title>
          <v-card-text>
            <v-text-field
              placeholder="Email"
              v-model="email"
              outlined
            ></v-text-field>
            <v-text-field
              placeholder="Password"
              v-model="password"
              type="password"
              outlined
            ></v-text-field>
            <v-btn color="success" @click="onSubmit" block>Enviar</v-btn>
          </v-card-text>
        </v-card>
      </v-col>
      <v-col cols="3"></v-col>
    </v-row>
  </div>
</template>

<script>
export default {
  data() {
    return {
      email: '',
      password: '',
    }
  },
  methods: {
    async onSubmit() {
      try {
        if (this.email.length < 4 || this.password.length < 2) {
          alert('Campos requeridos')
        }
        const body = JSON.stringify({
          email: this.email,
          password: this.password,
        })

        const res = await fetch('http://localhost:4500/api/user/sign-in', {
          method: 'post',
          headers: {
            'Content-Type': 'application/json',
          },
          body,
        })
        const data = await res.json()
        if (data.err) {
          alert(data.err)
          return
        }
        console.log({ data })

        localStorage.setItem('token', data.token)
        localStorage.setItem('email', data.user.email)
        localStorage.setItem('admin', data.user.admin)
        localStorage.setItem('avatar', data.user.avatar)
        localStorage.setItem('userId', data.user._id)

        this.$router.push('/home')
      } catch (err) {
        alert(err.message)
      }
    },
  },
}
</script>
