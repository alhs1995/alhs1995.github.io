<template>
  <div class="main">
    <div class="wrapper">
      <Nuxt />
    </div>
    <footer>
      ©2022 alhs1995
    </footer>
  </div>
</template>

<script>
export default {
  name: 'LayoutFront'
}
</script>

<style >
  .main{
    @apply w-auto h-auto min-h-screen p-0 flex flex-col bg-gray-100;
  }
  .wrapper{
    @apply flex-grow;
  }
</style>
