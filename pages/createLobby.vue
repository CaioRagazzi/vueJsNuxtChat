<template>
  <div class="container">
    <b-form v-if="show" @submit.prevent="onSubmit" @reset="onReset">
      <b-form-group
        id="input-group-1"
        label="Lobby Name:"
        label-for="input-1"
      >
        <b-form-input
          id="input-1"
          v-model="form.email"
          required
          placeholder="Enter lobby name"
        />
      </b-form-group>

      <b-form-group id="input-group-2" label="Your Name:" label-for="input-2">
        <b-form-input id="input-2" v-model="form.name" required placeholder="Enter name" />
      </b-form-group>

      <b-button type="submit" variant="primary">Submit</b-button>
      <b-button type="reset" variant="danger">Reset</b-button>
      <b-button @click="back()">Back</b-button>
    </b-form>
  </div>
</template>

<script>
export default {
  data () {
    return {
      show: true,
      form: { email: '', name: '' }
    }
  },
  methods: {
    onSubmit () {
      console.log(this.form.email, this.form.name)
    },
    onReset () {
      console.log('reset')
    },
    back () {
      this.$router.back()
    }
  }
}
</script>

<style>
.container {
  margin: 0 auto;
  min-height: 100vh;
  display: flex;
  justify-content: center;
  align-items: center;
  text-align: center;
}
</style>
