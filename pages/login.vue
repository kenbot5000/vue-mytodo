<template>
  <v-card width="450" class="ma-auto">
    <v-card-title>
      <h1 class="display-1">
        Welcome!
      </h1>
    </v-card-title>
    <v-card-text>
      <v-form>
        <v-text-field v-model="user.username" label="Username" />
        <v-text-field v-model="user.password" label="Password" type="password" />
      </v-form>
    </v-card-text>
    <v-divider />
    <v-card-actions>
      <RegConfirmationDialog @registerUser="submitLoginForm(true)" />
      <v-btn color="info" class="ml-2" @click="submitLoginForm(false)">
        Log In
      </v-btn>
    </v-card-actions>
  </v-card>
</template>

<script>
import axios from 'axios'
import RegConfirmationDialog from '../components/RegConfirmationDialog'

export default {
  components: {
    RegConfirmationDialog
  },
  layout: 'login',
  data () {
    return {
      user: {
        username: '',
        password: ''
      }
    }
  },
  methods: {
    async submitLoginForm (registering) {
      if (registering) {
        // const users = await axios.get('/api/users')
        console.log('R')
      } else {
        console.log('L')
      }
    }
  }
}
</script>

<style>
  .v-application--wrap {
    background-image: url("./../static/loginbg3.webp");
    background-size: cover;
    background-position-y: -500px;
  }
</style>
