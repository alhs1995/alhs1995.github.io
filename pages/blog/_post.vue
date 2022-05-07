<template>
  <div class="article">
    <h1>{{ Page.title }}</h1>
    <div class="tags">
      標籤：
      <PostTag v-for="tag in Page.tags" :key="tag" :text="tag" :link="`/blog/post-category/${tag}`" />
    </div>
    <div class="time">
      <!-- <div class="cTime">
        發表時間：{{ new Date(Page.createdAt).toLocaleString() }}
      </div> -->
      <div class="uTime">
        最後更新時間：{{ new Date(Page.updatedAt).toLocaleString() }}
      </div>
    </div>
    <hr>
    <nuxt-content :document="Page" />
  </div>
</template>

<script>
import '@/assets/css/post-content.css'
export default {
  layout: 'LayoutBlog',
  data () {
    return {
      Page: {}
    }
  },
  created () {
    this.fetchPosts(this.$route.params.post)
  },
  methods: {
    async fetchPosts (post) {
      this.Page = await this.$content('articles', post).fetch()
    }
  }
}
</script>
<style scoped>
  .article{
    @apply p-3 rounded-xl border-2 m-3 min-h-full;
  }
  h1{
    @apply text-4xl font-semibold;
  }
  .tags{
    @apply text-green-500 w-auto pt-2;
  }
  .time{
    @apply pt-1;
  }
  .time div{
    @apply text-blue-900;
  }
  hr{
    @apply mb-2;
  }
</style>
