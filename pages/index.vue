<!-- pages/index.vue -->
<template>
  <div>
    <h1>歡迎來到首頁</h1>
    <AppAlert>
      這是首頁的內容
    </AppAlert>
    <NuxtLink to="/intro">前往關於頁面</NuxtLink>
    <Figure
    imageUrl="/drawings/自設_人物.png"
      :dialogs="[
        '歡迎來到我的網站！',
        '如果想了解我的資訊，請點擊關於介面或是<a href=\'/intro\' class=\'dialog-link\'>這裡</a>！',
        '如果想了解期末專題的部分，請點擊期末專題介面或是<a href=\'/final\' class=\'dialog-link\'>這裡</a>！',
        'See you next time!'
      ]"
    />
  </div>
</template>

<script>
import Figure from '@/components/figure.vue'

export default {
  name: 'App',
  components: {
    Figure
  }
}
</script>