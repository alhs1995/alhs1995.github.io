<template>
  <div class="category">
    <div class="top">
      <h1>
        分類：{{ $route.params.category }}
      </h1>
      <hr>
    </div>
    <div class="middle">
      <post-card v-for="article in Page" :key="article.slug" :body="article" />
    </div>
    <div class="foot">
      <div class="prev">
        <button class="btn" :disabled="nowPage <= 1" @click="goPage(pageControl.prev)">
          上一頁
        </button>
      </div>
      <div class="next">
        <button class="btn" :disabled="Page.length < 4" @click="goPage(pageControl.next)">
          下一頁
        </button>
      </div>
    </div>
  </div>
</template>

<script>
export default {
  layout: 'LayoutBlog',
  data () {
    return {
      Page: [],
      nowPage: 0
    }
  },
  head () {
    return {
      title: this.$route.params.category + 'AL的隨筆部落',
      meta: [
        { charset: 'utf-8' },
        { name: 'viewport', content: 'width=device-width, initial-scale=1' },
        { hid: 'description', name: 'description', content: '' },
        { hid: 'keywords', name: 'keywords', content: this.$route.params.category }
      ]
    }
  },
  computed: {
    pageControl () {
      const routePath = `/blog/post-category/${this.$route.params.category}`
      return {
        next: routePath + '/' + (this.nowPage + 1),
        prev: this.nowPage > 2 ? routePath + '/' + (this.nowPage - 1) : routePath
      }
    }
  },
  created () {
    this.fetchPosts(this.$route.params.category, this.$route.params.page)
    this.nowPage = this.$route.params.page ? this.$route.params.page : 1
  },
  methods: {
    async fetchPosts (category, page = 1) {
      this.Page = await this.$content('articles')
        .only(['title', 'tags', 'excerpt', 'slug', 'createdAt'])
        .where({ tags: { $contains: category } })
        .sortBy('createdAt', 'asc')
        .skip((3 * (page - 1)))
        .limit(4)
        .fetch()
    },
    goPage (path) {
      this.$route.push(path)
    }
  }
}
</script>

<style scoped>
  .category{
    @apply pt-10 px-5 h-full flex flex-col;
  }
  .middle{
    @apply flex-grow;
  }
  .foot{
    @apply grid grid-cols-2 py-5 text-center;
  }
  h1{
    @apply text-6xl text-center;
  }
  hr{
    @apply my-3;
  }
  button.btn{
    @apply text-gray-600 border border-gray-600 rounded-full px-6 py-2;
  }
  button.btn:not(:disabled):hover{
    @apply text-gray-100 bg-gray-600;
  }
  button.btn:disabled{
    @apply text-gray-300 border-gray-300;
  }
</style>
