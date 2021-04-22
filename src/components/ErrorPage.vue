<template>
  <div>
    <v-row justify="center" align="center">

      <v-col align="center" sm="12">
        <h1 v-if="error.statusCode === 404">
          {{ pageNotFound }}
        </h1>
        <h1 v-else>
          {{ otherError }}
        </h1>
      </v-col>

    </v-row>

    <v-row justify="center" align="center">
      <NuxtLink to="/">
        Home page
      </NuxtLink>
    </v-row>

  </div>
</template>

<script>
export default {
  name: "ErrorPage",
  props: {
    error: {
      type: Object,
      default: null
    }
  },
  data () {
    return {
      pageNotFound: '404 Not Found',
      otherError: 'An error occurred'
    }
  },
  head () {
    const title =
        this.error.statusCode === 404 ? this.pageNotFound : this.otherError
    return {
      title
    }
  }
}
</script>

<style scoped>

</style>