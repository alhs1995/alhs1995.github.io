<template>
  <nuxt-link class="tag" :to="link">
    <PathIcon :path="mdiTag" stroke="#065f46" fill="none" prop-class="h-6 w-6 inline-block" />
    {{ text }}
  </nuxt-link>
</template>

<script>
import { mdiTag } from '@mdi/js'
import PathIcon from '~/components/PathIcon.vue'
export default {
  components: {
    PathIcon
  },
  props: {
    link: {
      type: String,
      default: '/blog'
    },
    text: {
      type: String,
      default: ''
    }
  },
  data: () => ({
    mdiTag
  })
}
</script>

<style scoped>
  a.tag{
    @apply inline-block bg-green-300 mx-1 p-1 rounded-3xl text-green-700;
  }
  a.tag:hover >>> svg path{
    fill: #065f46;
  }
</style>
