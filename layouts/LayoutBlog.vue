<template>
  <div class="main">
    <div class="wrapper">
      <div class="left-side">
        <div class="top">
          <h1 class="text-5xl text-center pt-9">
            AL的隨筆部落
          </h1>
          <p class="text-center pt-3">
            分享生活的感悟與學習經驗
          </p>
        </div>
        <div class="side">
          <nuxt-link class="side-link" to="/">
            <span>
              關於我
            </span>
          </nuxt-link>
          <nuxt-link class="side-link" to="/blog">
            <span>
              最新發表
            </span>
          </nuxt-link>
          <nuxt-link class="side-link" to="/blog/post-category">
            <span>
              分類
            </span>
          </nuxt-link>
          <!-- <nuxt-link class="side-link" to="/blog">
            <span>
              系列文
            </span>
          </nuxt-link> -->
        </div>
        <footer class="text-center">
          ©2022 alhs1995
        </footer>
      </div>
      <div class="main-context">
        <Nuxt />
      </div>
      <div class="right-side">
        <!--  -->
      </div>
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
    @apply flex-grow mx-11 mt-11 mb-7 rounded-3xl shadow-lg flex flex-col justify-around;
  }
  .side-link{
    @apply text-center text-3xl inline;
  }
  .side-link span:first-child{
    @apply relative;
    z-index: 20;
  }
  .side-link:hover span{
    @apply bg-transparent shadow-lg rounded-lg underline;
  }
  .side-link:hover span::before{
    content: '';
    @apply bg-blue-300 w-full h-full block absolute opacity-40 rounded-lg;
    top: 30%;
    left: 10%;
    z-index: -1;
  }
  .main-context{
    @apply flex-grow max-h-screen overflow-y-auto overflow-x-hidden;
    -ms-overflow-style: none;  /* IE and Edge */
    scrollbar-width: none;  /* Firefox */
  }
  .main-context::-webkit-scrollbar {
    display: none;
  }
  .right-side{
    background-image: linear-gradient(#f3f4f6aa, #f3f4f6aa), url('~/assets/img/right-bg.jpg');
    background-repeat: repeat;
    background-size: cover;
    flex: 0 0 15%;
  }
</style>
