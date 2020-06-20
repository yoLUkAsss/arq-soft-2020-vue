<template>
  <v-container>
      <v-form ref="form" v-model="valid" lazy-validation >

        <v-row>
          <v-col cols="12" md="6">
            <v-text-field v-model="form.username" :rules="validationForm.username" label="Usuario" required></v-text-field>
          </v-col>
          <v-col cols="12" md="6">
            <v-text-field v-model="form.password" :rules="validationForm.password" :type="'password'" label="Contrasenia" required></v-text-field>
          </v-col>
        </v-row>

        <v-btn color="error" class="mr-4" @click="reset" > Limpiar Formulario </v-btn>
        <v-btn color="success" @click="login"> Iniciar Sesion </v-btn>
      </v-form>
  </v-container>
</template>

<script>
// import Users from '../../services/users'

export default {
  data: () => ({
    form: {
      username: '',
      password: ''
    },
    validationForm: {
      username: [
        v => !!v || 'Username es requerido'
      ],
      password: [
        v => !!v || 'Contrasenia es requerido'
      ]
    },
    valid: true
  }),

  methods: {
    validate () {
      this.$refs.form.validate()
    },
    reset () {
      this.$refs.form.reset()
    },

    async login () {
      alert('No implementado aun')
    //   const response = await Users.create(this.form)
    //   if (response !== 'undefined') {
    //     this.$store.commit('login', response.username)
    //   }
    }
  }
}
</script>

<style>

</style>
