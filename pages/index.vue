<template>
  <div class="min-h-full grid grid-rows-5">
    <div class="row-span-2 grid grid-rows-4 justify-center justify-items-center justify-self-center p-1">
      <img :src="PersonalIcon" class="personal">
      <div class="text-center">
        <p class="text-4xl">
          Lee, You-Rong
        </p>
        <p class="text-xl">
          Front-end Developer / System Designer
        </p>
      </div>
      <div>
        <p class="flag">
          This world is worth fighting for
        </p>
      </div>
    </div>
    <div class="row-span-3">
      <PathIcon :path="mdiLinkedin" />
    </div>
  </div>
</template>

<script>
import { mdiLinkedin } from '@mdi/js'
import PathIcon from '~/components/PathIcon.vue'
import PersonalIcon from '~/assets/img/PersonalIcon-small.jpeg'
export default {
  name: 'IndexPage',
  components: {
    PathIcon
  },
  layout: 'LayoutFront',
  data () {
    return {
      PersonalIcon,
      mdiLinkedin
    }
  }
}
</script>

<style>
  .personal{
    @apply object-cover h-40 w-40 rounded-full object-top border-2 border-gray-400 shadow-xl row-span-2;
  }
  .flag{
    @apply border-2 shadow-xl border-gray-300 rounded p-2;
  }
</style>
