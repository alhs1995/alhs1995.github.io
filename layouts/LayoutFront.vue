<template>
  <div class="main">
    <div class="wrapper">
      <Nuxt />
    </div>
    <footer class="text-center">
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
    background: linear-gradient(to top right, #fef2f2, #fffbeb, #fdf2f8);
  }
  .wrapper{
    @apply flex-grow flex justify-center;
  }
</style>
