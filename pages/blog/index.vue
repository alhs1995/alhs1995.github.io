<template>
  <div class="w-full">
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
      .sortBy('createdAt', 'asc')
      .fetch()
    console.log(articles)
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
