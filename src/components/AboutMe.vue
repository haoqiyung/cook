<script lang="ts" setup>
import VueAboutMe from 'vue-about-me'
import 'vue-about-me/style.css'
import { isDark } from '~/composables'

const copyright = {
  name: 'Cook',
  repo: 'haoqiyung/cook',
  color: '#0078E7',
  iconUrl: 'https://cook.wasenk.cf',
  author: 'HaoQi',
  authorUrl: 'https://cook.wasenk.cf',
}

const links = [
  {
    type: 'github',
    label: 'GitHub: HaoQi',
    href: 'https://github.com/haoqiyung',
  },
  {
    type: 'blog',
    label: '博客：HaoQi',
    href: 'http://haoqi7.github.io',
  },
]
</script>

<template>
  <VueAboutMe :is-dark="isDark" :copyright="copyright" :links="links" />
</template>
