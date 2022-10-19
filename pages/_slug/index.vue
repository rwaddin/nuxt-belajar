<template>
  <div>
    <h1>Lorem ipsum dolor sit amet, consectetur adipisicing elit. Praesentium, temporibus.</h1>
    <pre>{{posts}}</pre>
  </div>
</template>

<script>
export default {
  name: "index",
  data(){
    return {
      posts: []
    }
  },
  async fetch() {
    //https://api.nuxtjs.dev/posts
    let slug = this.$route.params.slug;
    this.posts = await this.$axios.$get(`https://api.jikan.moe/v4/anime?q=${slug}&limit=2`)
  },
}
</script>

<style scoped>

</style>
