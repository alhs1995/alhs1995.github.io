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
  head () {
    return {
      title: 'AL的隨筆部落',
      meta: [
        { charset: 'utf-8' },
        { name: 'viewport', content: 'width=device-width, initial-scale=1' },
        { hid: 'description', name: 'description', content: '' },
        { hid: 'keywords', name: 'keywords', content: '' }
      ]
    }
  }
}
</script>

<style>
</style>
