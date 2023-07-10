<template>
  <b-row align-h="center">
    <b-col cols="6">
      <h2 class="text-center">Login</h2>
  <b-form @submit.prevent="handleSubmit">
    <b-form-group label="Username" label-for="email">
      <b-form-input id="email" v-model="email" type="email" required>
    </b-form-input>
    </b-form-group>
    <b-form-group label="Password" label-for="password">
      <b-form-input id="password" label="Password" v-model="password" type="password" required>
    </b-form-input>
    </b-form-group>
    <b-button type="submit" variant="primary">Log in</b-button>
  </b-form>
    </b-col>
</b-row>
</template>
 <script>
 export default {
  auth: 'guest',
  data() {
    return {
      email: '',
      password: '',
    };
  },
  methods: {
    handleSubmit() {
      const data = {
        email: this.email,
        password: this.password,
      };
      try {

        this.$auth.loginWith('local', {
        data: data
      }) ;
      } catch (error) {
        console.error(error);
      }
    },
  },
};
</script>
