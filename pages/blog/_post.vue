<template>
  <div class="article">
    <h1>{{ Page.title }}</h1>
    <div class="tags">
      標籤：
      <nuxt-link v-for="tag in Page.tags" :key="tag" class="tag" to="/blog">
        <PathIcon :path="mdiTag" stroke="#065f46" fill="none" prop-class="h-6 w-6 inline-block" />
        {{ tag }}
      </nuxt-link>
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
import { mdiTag } from '@mdi/js'
export default {
  layout: 'LayoutBlog',
  data () {
    return {
      mdiTag,
      Page: {}
    }
  },
  mounted () {
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
  .tag{
    @apply inline-block bg-green-300 mx-1 p-1 rounded-3xl text-green-700;
  }
  >>>.tag:hover svg path{
    fill: #065f46;
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
