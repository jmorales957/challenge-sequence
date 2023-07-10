<template>
  <header id="navbar-wrapper">
    <client-only>
      <b-navbar toggleable="sm" type="light" variant="light" class="border shadow-sm">
        <b-navbar-toggle target="nav-library"></b-navbar-toggle>
        <b-navbar-brand>Sequences</b-navbar-brand>

        <b-collapse v-if="this.$auth.loggedIn" id="nav-library" is-nav>
          <b-navbar-nav>
            <nuxt-link
          v-slot="{ isActive, navigate, href }"
          :to="{ name: 'sequences-create' }"
          custom
        >
        <b-nav-item :isActive="isActive" :href="href" @click="navigate">Create sequences</b-nav-item>
            </nuxt-link>

            <nuxt-link
          v-slot="{ isActive, navigate, href }"
          :to="{ name: 'sequences-total' }"
          custom
        >
        <b-nav-item :isActive="isActive" :href="href" @click="navigate">Total sequences</b-nav-item>
            </nuxt-link>
      </b-navbar-nav>
          <b-navbar-nav class="ml-auto">
          <b-nav-item-dropdown right>
            <!-- Using 'button-content' slot -->
            <template #button-content>
              <em>User</em>
            </template>
            <b-dropdown-item @click="logOut">Sign Out</b-dropdown-item>
          </b-nav-item-dropdown>
          </b-navbar-nav>
        </b-collapse>
      </b-navbar>
    </client-only>
  </header>
</template>

<script>
export default {
  name: "NavBar",
  methods: {
    async logOut() {
      try {
        await this.$auth.logout()
      } catch (e) {
      }
    },
  },
}
</script>
