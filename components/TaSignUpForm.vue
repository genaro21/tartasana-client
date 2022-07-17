<template>
  <div class="ta-sign-up-form">
    <v-row>
      <v-col cols="3"></v-col>
      <v-col cols="6">
        <v-card>
          <v-card-title class="d-flex justify-center">Sign Up</v-card-title>
          <v-card-text>
            <v-file-input
              v-model="avatar"
              placeholder="Introduce tu foto"
              prepend-icon=""
              outlined
              name="avatar"
              required
            ></v-file-input>
            <v-text-field
              placeholder="Nombre"
              v-model="firstName"
              name="firstName"
              outlined
              required
            ></v-text-field>
            <v-text-field
              placeholder="Apellidos"
              v-model="lastName"
              name="lastName"
              outlined
              required
            ></v-text-field>
            <v-text-field
              placeholder="Teléfono"
              v-model="phone"
              name="phone"
              outlined
              required
            ></v-text-field>
            <v-text-field
              placeholder="Email"
              v-model="email"
              name="email"
              outlined
              required
            ></v-text-field>
            <v-text-field
              placeholder="Contraseña"
              name="password"
              v-model="password"
              outlined
              required
            ></v-text-field>
            <v-text-field
              placeholder="Repite contraseña"
              name="password2"
              v-model="password2"
              outlined
              required
            ></v-text-field>
            <v-btn color="success" block @click="onSubmit">Enviar</v-btn>
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
      avatar: undefined,
      valid: true,
      password: '',
      password2: '',
      firstName: '',
      lastName: '',
      phone: '',
      email: '',
    }
  },
  methods: {
    async onSubmit() {
      if (this.password !== this.password2) {
        alert('Contraseñas diferentes')
        return
      }
      const formData = new FormData()

      formData.enctype = 'multipart/form-data'
      formData.append('avatar', this.avatar)
      formData.append('firstName', this.firstName)
      formData.append('lastName', this.lastName)
      formData.append('phone', this.phone)
      formData.append('email', this.email)
      formData.append('password', this.password)

      try {
        const res = await fetch('http://localhost:4500/api/user/sign-up', {
          method: 'POST',
          body: formData,
        })
        const data = await res.json()
        if (data.err) {
          alert(data.err)
        } else {
          this.$router.push('/sign-in')
        }
      } catch (err) {
        alert(err.message)
      }
    },
  },
}
</script>
