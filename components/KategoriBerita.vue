<template>
  <div id="listCategory">
    <h1 class="my-5 text-center">Category News</h1>
    <v-layout row class="mx-10">
      <v-container
        v-for="category in categoryNews"
        :key="category.id"
        flex
        xs12
        sm6
        md4
        lg3
      >
        <v-hover v-slot="{ hover }">
          <v-card elevation="2" outlined shaped>
            <v-img :src="category.gambar" max-height="150" />
            <v-fade-transition>
              <v-overlay v-if="hover" absolute color="#DBBAE8">
                <v-btn class="primary" small @click="fetchNews(category.nama)"
                  >{{ category.nama }}
                </v-btn>
              </v-overlay>
            </v-fade-transition>
          </v-card>
        </v-hover>
      </v-container>
    </v-layout>
  </div>
</template>

<script>
export default {
  computed: {
    categoryNews() {
      return this.$store.state.listCategories
    },
  },
  methods: {
    fetchNews(value) {
      this.$store.dispatch('getCategory', value)
      this.$router.push({
        name: 'berita-category',
        params: { category: value },
      })
    },
  },
}
</script>
