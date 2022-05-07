<template>
  <div class="category">
    <h1>分類</h1>
    <hr>
    <div class="tags">
      <PostTag v-for="tag in tags" :key="tag" :text="tag" :link="`/blog/post-category/${tag}`" />
    </div>
  </div>
</template>

<script>
export default {
  name: 'PostCategory',
  layout: 'LayoutBlog',
  async asyncData ({ $content }) {
    const articles = await $content('articles')
      .only(['tags'])
      .fetch()
    const tags = [...new Set([].concat(...articles.map(e => e.tags)))]
    return {
      tags
    }
  }
}
</script>

<style scoped>
  .category{
    @apply pt-10 px-5;
  }
  h1{
    @apply text-6xl text-center;
  }
  hr{
    @apply my-3 border-gray-400;
  }
  .tags{
    @apply text-green-500 w-auto;
  }
</style>
