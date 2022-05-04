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
        <nuxtx-link v-for="tag in body.tags" :key="tag" class="tag">
          <PathIcon :path="mdiTag" stroke="#065f46" fill="none" prop-class="h-6 w-6 inline-block" />
          {{ tag }}
        </nuxtx-link>
      </div>
      <div class="upTime">
        時間：{{ new Date(body.createdAt).toLocaleString() }}
      </div>
    </div>
  </div>
</template>

<script>
import { mdiTag } from '@mdi/js'
import PathIcon from '~/components/PathIcon.vue'
export default {
  components: {
    PathIcon
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
  .tag{
    @apply inline-block bg-green-300 mx-1 p-1 rounded-3xl text-green-700;
  }
  .upTime{
    @apply text-blue-900;
  }
</style>
