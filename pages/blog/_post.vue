<template>
  <div class="article">
    <h1>{{ Page.title }}</h1>
    <nuxt-content :document="Page" />
  </div>
</template>

<script>
export default {
  layout: 'LayoutBlog',
  data () {
    return {
      Page: {}
    }
  },
  mounted () {
    this.fetchPosts(this.$route.params.post)
  },
  methods: {
    async fetchPosts (post) {
      this.Page = await this.$content('articles', post).fetch()
      console.log(this.Page)
    }
  }
}
</script>
