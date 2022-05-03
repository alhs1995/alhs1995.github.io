<template>
  <div class="w-11/12 flex">
    <post-card v-for="article in articles" :key="article.slug" :body="article" />
  </div>
</template>

<script>
import postCard from '@/components/postCard.vue'
export default {
  name: 'IndexPage',
  components: {
    postCard
  },
  layout: 'LayoutBlog',
  async asyncData ({ $content }) {
    const articles = await $content('articles')
      .only(['title', 'slug', 'excerpt'])
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
