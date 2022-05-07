<template>
  <div class="w-full">
    <post-card v-for="article in articles" :key="article.slug" :body="article" />
  </div>
</template>

<script>
export default {
  name: 'IndexPage',
  layout: 'LayoutBlog',
  async asyncData ({ $content }) {
    const articles = await $content('articles')
      .only(['title', 'tags', 'excerpt', 'slug', 'createdAt'])
      .sortBy('createdAt', 'asc')
      .fetch()
    return {
      articles
    }
  },
  data () {
    return {
    }
  }
}
</script>

<style>
</style>
