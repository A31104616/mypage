<!-- pages/index.vue -->
<template>
  <div class="figure-container">
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

<style scoped>
.figure-container {
  width: 100%;
  flex-grow: 1;
  display: flex;
  justify-content: center;
  align-items: center;
  margin: 0;
  padding: 0;
  box-sizing: border-box;
}
</style>