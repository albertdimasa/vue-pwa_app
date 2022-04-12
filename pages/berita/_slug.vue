<template>
  <detailBerita :news="oneNews" />
</template>

<script>
import detailBerita from '~/components/DetailBerita.vue'
export default {
  name: 'DetailBerita',
  components: {
    detailBerita,
  },
  computed: {
    oneNews() {
      return this.$store.state.oneNews
    },
  },
  created() {
    this.getNews(this.$route.params.slug)
  },
  methods: {
    getNews(slug) {
      this.$store.dispatch('getNews', slug)
    },
  },
}
</script>

<style></style>
