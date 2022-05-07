<template>
  <div class="card">
    <h1>{{ body.title }}</h1>
    <hr>
    <div class="content">
      <nuxt-content :document="{ body: body.excerpt }" />
      ...
      <nuxt-link class="continue" :to="'/blog/'+body.slug">
        繼續閱讀
      </nuxt-link>
    </div>
    <hr>
    <div class="card-footer">
      <div class="tags">
        標籤：
        <PostTag v-for="tag in body.tags" :key="tag" :text="tag" :link="`/blog/post-category/${tag}`" />
      </div>
      <div class="upTime">
        時間：{{ new Date(body.createdAt).toLocaleString() }}
      </div>
    </div>
  </div>
</template>

<script>
import { mdiTag } from '@mdi/js'
import PostTag from '~/components/PostTag.vue'
export default {
  components: {
    PostTag
  },
  props: {
    body: {
      type: Object,
      default: () => ({})
    }
  },
  data () {
    return {
      mdiTag
    }
  }
}
</script>

<style scoped>
  .card{
    @apply rounded-xl shadow-md w-auto m-3 block p-3;
  }
  h1{
    @apply text-3xl font-semibold mb-2;
  }
  .content{
    @apply m-2;
  }
  .continue{
    @apply text-gray-300 underline;
  }
  .continue:hover, .continue:visited{
    @apply text-gray-600 underline;
  }
  .card-footer{
    @apply w-full flex justify-end mt-2 items-center;
  }
  .tags{
    @apply text-green-500 w-auto;
  }
  .upTime{
    @apply text-blue-900;
  }
</style>
