<template>
    <div class="about-container">
        <div class = "content">
        <div class="profile-card relative">
        <!-- 嵌入 iframe 當作預覽畫面 -->
            <iframe
                :src="previewUrl"
                class="w-full h-[400px]"
                style="
                    border: none;
                    border-bottom: 1px solid #eee;
                    pointer-events: none;
                "
            ></iframe>
            <!-- 點擊跳轉連結層 -->
            <a
                :href="previewUrl"
                target="_blank"
                class="absolute inset-0 z-10"
                aria-label="點擊前往預覽網站"
            ></a>
        </div>
        <!-- 介紹區塊 -->
        <div class="profile-content">
            <section class="about-section">
            <h2>{{ title }}</h2>
            <p>{{ description }}</p>

            <h2>網站介紹</h2>
            <h3>主頁</h3>
            <p>展示繪畫及攝影兩類別中最多的標籤的作品，最多展示五張該類別的圖片。如果對該標籤的主題有興趣，可點擊該標籤以查看更多該主題的圖片</p>
            </section>
        </div>
        </div>
    </div>
</template>

<script setup>
const previewUrl = 'https://final-project-sage-eta.vercel.app'
const title = '期末專題網站'
const description =
  '這是一個展示我專案與作品的網站，包含互動式設計、響應式佈局與使用者友善的介面設計，歡迎點擊上方圖片預覽完整網頁。'
</script>

<style scoped>
.about-container {
  min-height: 100vh;
  width: 100%;
  display: flex;
  flex-direction: column;
  justify-content: center;
  align-items: center;
  box-sizing: border-box; /* 確保 padding 不會增加容器大小 */
}
.content {
  width: 800px;
  margin: 1rem;
  background-color: #ffffff;
  border-radius: 15px;
}

.profile-card {
  max-width: 800px;
  width: 100%;
  background: white;
  border-radius: 15px;
  box-shadow: 0 4px 6px rgba(0, 0, 0, 0.1);
  overflow: hidden;
  position: relative;
}

.profile-content {
  padding: 1rem;
}

h2 {
  color: #333;
  margin-bottom: 1rem;
  border-bottom: 2px solid #eee;
  padding-bottom: 0.5rem;
}

h1 {
  padding-bottom: 1rem;
}

h2 {
  color: #333;
  margin-bottom: 1rem;
  border-bottom: 2px solid #eee;
  padding: 0.5rem;
  font-size: 1.5rem;
  font-weight: bold;
}

h3 {
  color: #333;
  padding: 0.25rem 0;
  font-size: 1.2rem;
  font-weight: bold;
}

p{
    color: #333;
    padding: 0.75rem;
}

@media (max-width: 768px) {
  .profile-card {
    border-radius: 0;
  }
}
</style>