<template>
  <b-row align-h="center">
    <b-col cols="8">
      <h1>Welcome to Challenge Sequences</h1>
  <nuxt-link
    v-slot="{ isActive, navigate, href }"
    :to="{ name: 'login' }"
    custom
  >
    <b-button :href="href" @click="navigate" variant="outline-primary">Login</b-button>
  </nuxt-link>
    </b-col>
  </b-row>

</template>

<script>
export default {
  name: 'IndexPage',
  auth: 'guest',
}
</script>
