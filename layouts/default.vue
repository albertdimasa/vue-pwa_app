<template>
  <v-app>
    <Header />

    <v-main>
      <Nuxt />
    </v-main>
  </v-app>
</template>

<script>
import Header from '@/components/NavbarHead.vue'
export default {
  name: 'DefaultLayout',
  components: { Header },
}
</script>

<style scoped></style>
