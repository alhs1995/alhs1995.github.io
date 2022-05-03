<template>
  <div class="card">
    <h1>{{ body.title }}</h1>
    <nuxt-content :document="{ body: body.excerpt }" />
  </div>
</template>

<script>
export default {
  props: {
    body: {
      type: Object,
      default: () => ({})
    }
  }
}
</script>

<style>
  .card{
    @apply rounded-3xl shadow-md;
  }
</style>
