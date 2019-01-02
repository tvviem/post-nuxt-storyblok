<template>
  <div>
    <TheHeader />
    <main>
      <nuxt/>
    </main>
  </div>
</template>

<script>
import TheHeader from '~/components/TheHeader/Header.vue'
export default {
  components: {
    TheHeader
  }
}
</script>
