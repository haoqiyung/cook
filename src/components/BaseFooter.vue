<script lang="ts" setup>
import { isClient } from '@vueuse/core'

const displayICP = ref(true)

onBeforeMount(() => {
  if (isClient)
    displayICP.value = ['cook.wasenk.cf', 'localhost', '127.0.0.1'].includes(window.location.hostname)
})

const commitSha = (import.meta.env.VITE_COMMIT_REF || '').slice(0, 7)
const now = import.meta.env.VITE_APP_BUILD_TIME
const buildDate = (new Date(parseInt(now) * 1000)).toLocaleDateString()
</script>

<template>
  <div p="4" class="flex flex-col justify-center items-center" text="sm">
    <div v-if="commitSha && buildDate" mb-2>
      <span>
        当前版本（{{ buildDate }}）:
      </span>
      <span>
        <a border="b-1 dashed" :href="`https://github.com/haoqiyung/cook/commit/${commitSha}`" target="_blank" alt="Cook | GitHub Commit">
          {{ commitSha }}
        </a>
      </span>
    </div>
    
    <div m="t-2" class="inline-flex justify-center items-center" text="xs">
      <a class="inline-flex justify-center items-center" style="color: #ea7b99" href="https://www.bilibili.com/blackboard/dynamic/306882" target="_blank">
        <span inline-flex>菜谱视频来源：</span>
        <div class="inline-flex" i-ri-bilibili-line />
        <span m="l-1" class="inline-flex" style="margin-top: 1px;">B 站</span>
      </a>
    </div>
    <div m="t-2" opacity="80" class="flex justify-center items-center">
      ©️&nbsp;<a href="https://github.com/haoqiyung/cook" target="_blank">Cook</a>
      <div text="xs" m="x-1" i-ri-cloud-line />
      <a href="https://haoqi7.github.io" target="_blank">HaoQi</a>
    </div>


  </div>
</template>
