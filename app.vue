<script lang="ts" setup>
import { AppConfigInput } from '@nuxt/schema'
import { AppSetup } from './utils/app'
import { ITheme } from './utils/theme'
// import { zh_init } from '~/assets/js/uselang'
AppSetup()
const theme = useState<ITheme>('theme.current')
const locale = useState<string>('locale.setting')
const app = useAppConfig() as AppConfigInput

useHead({
  title: app.name,
  titleTemplate: "%s | 深圳愛康健口腔醫院",
  meta: [
    { name: 'viewport', content: 'width=device-width, initial-scale=1, maximum-scale=1' },
    {
      hid: 'description',
      name: 'description',
      content: '愛康健集團是大灣區牙科連鎖機構，其口腔醫院為香港政府指定長者醫療券大灣區試點。（香港熱線: 6933 8128）14間門診有超過20種牙科治療項目，專注為港服務超過29年。',
    },
    {
      hid: 'Keywords',
      name: 'Keywords',
      content: '愛康健 深圳愛康健 深圳專業牙科中心 愛康健醫院 愛康健口腔醫院 深圳愛康健口腔醫院愛康健 CKJ愛康健齒科集團 愛康健齒科集團 深圳口腔專科醫院 深圳牙科醫院牙科服務內地牙科 深圳口腔專科 基本牙科 美容牙科 高階牙科',
    },
    {
      name: 'author',
      content: '愛康健口腔醫院',
    },
    { property: 'og:image', content: 'https://www.ckjhk.com/favicon.ico' }
  ],
  link: [
    { rel: 'shortcut icon', type: 'image/x-icon', href: '/favicon.ico' },
    { rel: 'icon', type: 'image/x-icon', href: 'https://www.ckjhk.com/favicon.ico' },
    { rel: 'apple-touch-icon', type: 'image/x-icon', href: 'https://www.ckjhk.com/favicon.ico' },
  ],
  script:[
    { type: 'text/javascript', src: '/common.js' },
  ]
})

onMounted(()=>{
  // zh_init()
  // 监听网络是否关闭
  // window.addEventListener('offline',(e)=>{
  //   console.log(e)
  // })

  // 全局弹窗
  // ElMessage({
  //   showClose: true,
  //   message: '表單提交成功！我們會盡快回覆閣下。',
  //   type: 'success',
  //   duration: 0
  // })
  // document.onkeydown = (even:any) =>{
  //   if(even.key === 'F9'){
  //     if(locale.value === 'zh')
  //       locale.value = 'hk'
  //     else
  //       locale.value = 'zh'
  //   }
  // }
  locale.value = 'hk'
})
</script>

<template>
  <Html lang="zh-hk">
    <Body
      class="antialiased duration-300 transition-colors text-gray-800 dark:text-gray-200 bg-white dark:bg-gray-900 overscroll-y-none"
    >
      <NuxtLayout>
        <PageMenuBar />
        <NuxtPage />
      </NuxtLayout>
      <noscript><img height="1" width="1" style="display:none" src="https://www.facebook.com/tr?id=2035768320098958&ev=PageView&noscript=1" /></noscript>
    </Body>
  </Html>
</template>
<style>
/* @media (prefers-reduced-motion: no-preference) {
    html {
        scroll-behavior: smooth;
    }
} */
</style>