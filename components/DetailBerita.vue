<template>
  <v-container>
    <v-img :src="news.media" max-width="60%" class="rounded-lg mb-3" />
    <h2>{{ news.title }}</h2>
    <h4 class="blue-grey--text">
      {{ news.author }} -
      {{ moment(news.publishedAt).locale('id').format('LLLL') }}
    </h4>
    <p class="mt-3">{{ news.summary }}</p>
    <v-btn class="secondary mr-5" @click="$router.back()">Kembali</v-btn>
    <v-btn :href="news.link" target="_blank" class="blue darken-4 white--text"
      >Baca selengkapnya</v-btn
    >
  </v-container>
</template>
<script>
export default {
  name: 'DetailNews',
  props: {
    // eslint-disable-next-line vue/require-default-prop
    news: Object,
  },
}
</script>
<style scoped></style>
