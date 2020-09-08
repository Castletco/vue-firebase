<template>
  <b-container>
    <h2>Formulario de Registro</h2>
    <b-row class="justify-content-center">
      <b-form @submit="onSubmit" @reset="onReset" v-if="show">
        <b-form-group
          id="input-group-1"
          label="Dirección Email:"
          label-for="input-1"
          description="No compartiremos tu e-mail con nadie más"
        >
          <b-form-input
            id="input-1"
            v-model="form.email"
            type="email"
            required
            placeholder="Enter email"
          ></b-form-input>
        </b-form-group>

        <b-form-group id="input-group-2" label="Contraseña:" label-for="input-2">
          <b-form-input
            id="text-password"
            type="password"
            v-model="form.password"
            aria-describedby="password-help-block"
            required
            placeholder="Enter password"
          ></b-form-input>
          <b-form-text id="password-help-block">
            Your password must be 8-20 characters long, contain letters and numbers, and must not
            contain spaces, special characters, or emoji.
          </b-form-text>
        </b-form-group>

        <b-button type="submit" variant="primary">Submit</b-button>
        <b-button type="reset" variant="danger">Reset</b-button>
      </b-form>
    </b-row>
  </b-container>
</template>

<script>
import { db } from '@/firebase'
export default {
  name: 'Login',
  data () {
    return {
      form: {
        email: '',
        password: ''
      },
      show: true
    }
  },
  methods: {
    onSubmit (evt) {
      evt.preventDefault()
      db.collection('users').add({
        email: this.form.email,
        password: this.form.password
      })
      // eslint-disable-next-line no-unused-expressions,no-sequences
      this.form.email = '',
      this.form.password = ''
    },
    async viewOne (petId) {
      try {
        const singlePetDoc = await db.collection('users').doc(petId).get()
        // once retrieved, the id is at the document level
        console.log(singlePetDoc.id)
        // and the contents of the document are available via data()
        const petDetails = singlePetDoc.data()
        console.log(petDetails.Name)
        console.log(petDetails.Colors)
      } catch (error) {
        console.log(error)
      }
    },
    onReset (evt) {
      evt.preventDefault()
      // Reset our form values
      this.form.email = ''
      this.form.password = ''
      // Trick to reset/clear native browser form validation state
      this.show = false
      this.$nextTick(() => {
        this.show = true
      })
    }
  }
}
</script>

<style scoped>

</style>
