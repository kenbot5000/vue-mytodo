<template>
  <v-dialog v-model="dialog" width="500">
    <template v-slot:activator="{ on, attrs }">
      <v-btn color="success" v-bind="attrs" v-on="on">
        Register
      </v-btn>
    </template>

    <v-card>
      <v-card-title>
        Are you sure you want to register?
      </v-card-title>
      <v-card-actions>
        <v-btn color="primary" @click="emitRegister()">
          Yes
        </v-btn>
      </v-card-actions>
    </v-card>
  </v-dialog>
</template>

<script>
export default {
  data () {
    return {
      dialog: false
    }
  },
  methods: {
    emitRegister () {
      this.$emit('registerUser')
      this.dialog = false
    }
  }
}
</script>

<style>

</style>
