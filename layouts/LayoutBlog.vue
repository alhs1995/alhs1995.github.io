<template>
  <div class="main">
    <div class="wrapper">
      <div class="left-side">
        <div class="top">
          <h1 class="text-5xl text-center pt-9">
            AL的隨筆部落
          </h1>
        </div>
        <div class="side">
          123
        </div>
        <footer class="text-center">
          ©2022 alhs1995
        </footer>
      </div>
      <div class="main-context">
        <Nuxt />
      </div>
      <div class="right-side"></div>
    </div>
  </div>
</template>

<script>
export default {
  name: 'LayoutBlog'
}
</script>

<style >
  .main{
    @apply w-auto h-auto min-h-screen p-0 flex flex-col bg-gray-100;
  }
  .wrapper{
    @apply flex-grow flex flex-row;
  }
  .left-side{
    @apply flex flex-col shadow-lg;
    background-image: linear-gradient(#f3f4f6aa, #f3f4f6aa), url('~/assets/img/left-bg.jpg');
    background-repeat: repeat;
    background-size: cover;
    flex: 0 0 20%;
  }
  .side{
    @apply flex-grow mx-11 mt-11 mb-7 rounded-3xl shadow-lg;
  }
  .main-context{
    @apply flex-grow;
  }
  .right-side{
    background-image: linear-gradient(#f3f4f6aa, #f3f4f6aa), url('~/assets/img/right-bg.jpg');
    background-repeat: repeat;
    background-size: cover;
    flex: 0 0 15%;
  }
</style>
