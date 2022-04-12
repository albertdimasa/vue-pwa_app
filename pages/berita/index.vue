<template>
  <div>
    <daftarBerita />
  </div>
</template>

<script>
import daftarBerita from '~/components/DaftarBerita.vue'
export default {
  name: 'DaftarBerita',
  components: { daftarBerita },
  middleware: 'to_home'
}
</script>
