<template>
  <div>
    <NavBar/>
    <main>
      <b-container class="my-4">
        <Nuxt/>
      </b-container>
    </main>
  </div>
</template>

<script>
export default {
  name: "Default",
  components:{
    NavBar: () => import('@/components/NavBar')
  }
}
</script>
