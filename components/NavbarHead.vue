<template>
  <v-app-bar app flat class="px-10">
    <img
      src="~static/logo.jpg"
      style="width: 50px; cursor: pointer"
      @click="categoryNull"
    />

    <v-spacer></v-spacer>
    <v-text-field
      v-model="search"
      class="mt-5"
      placeholder="Search"
      filled
      dense
      prepend-inner-icon="mdi-magnify"
    ></v-text-field>

    <v-btn icon :to="{ name: 'berita-kategori' }">
      <v-icon>mdi-shape</v-icon>
    </v-btn>
  </v-app-bar>
</template>
<script>
export default {
  data() {
    return {
      search: (this.$store.state.search = ''),
    }
  },
  watch: {
    search(value) {
      this.$store.dispatch('getSearch', value)
    },
  },
  methods: {
    categoryNull() {
      this.$store.dispatch('getCategory', '')
      this.search = ''

      this.$router.push({
        name: 'berita',
      })
    },
  },
}
</script>
