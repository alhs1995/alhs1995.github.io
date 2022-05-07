<template>
  <div class="w-11/12 flex flex-col justify-self-center">
    <div class="grid grid-rows-4 justify-center justify-items-center justify-self-center p-1">
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
        <span class="block mb-3 text-center">
          <PathIcon :path="mdiMapMarker" stroke="none" fill="green" prop-class="h-6 w-6 inline" />
          Kauhsiung, Taiwan
        </span>
        <span class="flag">
          This world is worth fighting for.
        </span>
      </div>
    </div>
    <div class="flex flex-col w-full">
      <div class="introduction">
        <div class="blocks">
          <span class="block-title">Skills</span>
          <span class="Skill-title">Web application</span>
          <div class="skill">
            <PathIcon :path="mdiVuejs" stroke="none" fill="green" prop-class="mr-3 h-6 w-6" />
            <span class="text-xl font-semibold block">VueJs</span>
          </div>
          <div class="skill">
            <PathIcon :path="mdiNuxt" stroke="none" fill="green" prop-class="mr-3 h-6 w-6" />
            <span class="text-xl font-semibold block">Nuxt</span>
          </div>
          <div class="skill">
            <PathIcon :path="mdiLanguageJavascript" stroke="none" fill="green" prop-class="mr-3 h-6 w-6" />
            <span class="text-xl font-semibold block">Javascript</span>
          </div>
          <span class="Skill-title">Web Design</span>
          <div class="skill">
            <PathIcon :path="mdiLanguageHtml5" stroke="none" fill="green" prop-class="mr-3 h-6 w-6" />
            <span class="text-xl font-semibold block">HTML</span>
          </div>
          <div class="skill">
            <PathIcon :path="mdiLanguageCss3" stroke="none" fill="green" prop-class="mr-3 h-6 w-6" />
            <span class="text-xl font-semibold block">CSS</span>
          </div>
          <div class="skill">
            <PathIcon :path="mdiSass" stroke="none" fill="green" prop-class="mr-3 h-6 w-6" />
            <span class="text-xl font-semibold block">SASS/SCSS</span>
          </div>
          <div class="skill">
            <PathIcon :path="mdiSvg" stroke="none" fill="green" prop-class="mr-3 h-6 w-6" />
            <span class="text-xl font-semibold block">SVG</span>
          </div>
          <span class="Skill-title">Other</span>
          <div class="skill">
            <PathIcon :path="mdiDatabase" stroke="none" fill="green" prop-class="mr-3 h-6 w-6" />
            <span class="text-xl font-semibold block">T-SQL</span>
          </div>
        </div>
        <div class="blocks">
          <span class="block-title">Educations</span>
          <h4 class="text-2xl text-yellow-500">
            Bachelor
          </h4>
          <span class="text-xl">Tunghai University</span>
          <span>Computer Science</span>
          <span>09/2013 ~ 07/2017</span>
        </div>
        <div class="blocks">
          <span class="block-title">Experiences</span>
          <div class="company">
            <span class="company-name">SHANDA INFORMATION CO.,LTD.<span class="text-lg inline">01/2021 ~ present</span></span>
            <span>Front-end web developer</span>
            <span>Contractor of InfoChamp Systems Corp.</span>
            <span>Engaged projects :</span>
            <ul>
              <li>Internal Department Management System - SD and Front-end web developer</li>
              <li>Alishan Forest Railway Safety Management Information System - SD and Full stack developer</li>
            </ul>
          </div>
          <div class="company">
            <span class="company-name">SKYTEK Industrial Co., Ltd.<span class="text-lg inline">09/2017 ~ 11/2020</span></span>
            <span>Full stack developer</span>
            <ul>
              <li>Administration systems for over 15 universities.- Full stack developer and Maintainer </li>
              <li>Sport talent class performance evaluation system for Taipei City. - Full stack developer and Maintainer </li>
              <li>Bring VueJS and SCSS into Company.</li>
            </ul>
          </div>
        </div>
      </div>
    </div>
    <div class="flex flex-row justify-center">
      <nuxt-link class="button" to="/blog" title="blog">
        <PathIcon :path="mdiPost" stroke="none" fill="#F59E0B" />
      </nuxt-link>
      <a class="button" href="http://github.com/alhs1995" target="_blank" title="github">
        <PathIcon :path="mdiGithub" stroke="none" fill="#F59E0B" />
      </a>
      <a class="button" href="http://www.linkedin.com/in/侑融-李-90680a218" target="_blank" title="linkedin">
        <PathIcon :path="mdiLinkedin" stroke="none" fill="#F59E0B" />
      </a>
    </div>
  </div>
</template>

<script>
import { mdiMapMarker, mdiVuejs, mdiNuxt, mdiLanguageHtml5, mdiLanguageJavascript, mdiLanguageCss3, mdiSass, mdiDatabase, mdiSvg, mdiPost, mdiGithub, mdiLinkedin } from '@mdi/js'
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
      mdiMapMarker,
      mdiVuejs,
      mdiNuxt,
      mdiLanguageHtml5,
      mdiLanguageJavascript,
      mdiLanguageCss3,
      mdiSass,
      mdiDatabase,
      mdiSvg,
      mdiPost,
      mdiGithub,
      mdiLinkedin
    }
  }
}
</script>

<style scoped>
  .personal{
    @apply object-cover h-44 w-44 rounded-full object-top border-2 border-gray-400 shadow-xl row-span-2;
  }
  .flag{
    @apply border-2 shadow-xl border-yellow-200 rounded p-2 opacity-40;
  }
  .introduction{
    @apply flex flex-row;
  }
  .blocks{
    @apply flex flex-col rounded-lg shadow-lg flex-grow mx-5 p-4;
  }
  .block-title{
    @apply font-bold text-4xl text-center block mb-4;
  }
  .skill{
    @apply content-end flex flex-row;
  }
  .Skill-title{
    @apply text-2xl font-medium;
  }
  .company span{
    @apply block;
  }
  .company ul{
    @apply list-disc ml-5;
  }
  .company-name{
    @apply text-2xl;
  }
  .company-name span{
    @apply inline text-lg ml-3;
  }
  .button{
    @apply border-2 rounded border-yellow-500 w-9 h-9 p-1 m-3;
  }
</style>
