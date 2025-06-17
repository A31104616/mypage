<template>
  <div class="about-container">
    <div class = "content">
      <div class="profile-content">
        <section class="about-section">
          <h2>{{ title }}</h2>
          <p>此網站為影像展示網站，展示內容可分為繪圖與攝影兩大類。使用者能分別瀏覽攝影或繪圖作品，並能透過標籤（Tag）搜尋作品。</p>
          <div class="skills-grid">
            <div class="skill-item">Nuxt 3</div>
            <div class="skill-item">Firestorage</div>
            <div class="skill-item">Firestore</div>
            <div class="skill-item">Router</div>
            <div class="skill-item">Composables</div>
            <div class="skill-item">RWD</div>
          </div>
        </section>
      </div>
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
          <h2>網站介紹</h2>
          <h3>主頁</h3>
          <p>展示繪畫及攝影兩類別中最多的標籤的作品，最多展示五張該類別的圖片。</p>
          <p>如果對該標籤的主題有興趣，可點擊該標籤以查看更多該主題的圖片，也可點擊作品以查看作品詳情。</p>
        
          <h3>頁首</h3>
          <p>展示網頁功能與搜尋列的功能列，搜尋列可以選擇搜尋繪畫或攝影主題的作品標籤。</p>

          <h3>繪圖 / 攝影</h3>
          <p>展示該主題作品的頁面，右上方的調整功能可以讓使用者根據裝置自行選擇作品卡片的顯示大小。</p>
          <p>可點擊作品底下標籤以查看更多帶有該標籤的圖片，也可點擊作品以查看作品詳情。</p>
          <p>作品詳情中，如果喜歡該作品可以點擊愛心以表示喜歡與支持該作品。</p>

          <h3>上傳</h3>
          <p>上傳影像至網頁的頁面，其中除了作品描述為選填外，其餘都是必填項目。</p>
          <p>上傳作品後將自動跳轉上傳的作品詳情頁面。</p>
        </section>
      </div>
    </div>
  </div>
</template>

<script setup>
const previewUrl = 'https://final-project-sage-eta.vercel.app'
const title = '期末專題網站'
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
  max-width: 800px;
  width: 100%;
  margin: 2rem;
  background-color: #ffffff;
  border-radius: 15px;
}

.profile-card {
  max-width: 800px;
  width: 95%;
  background: white;
  border-radius: 15px;
  box-shadow: 0 4px 6px rgba(0, 0, 0, 0.1);
  overflow: hidden;
  position: relative;
  margin: 0 auto; 
  margin-bottom: 1rem;
  transition: ease-in-out 0.3s;
}
.profile-card:hover {
  box-shadow: 0 6px 12px rgba(0, 0, 0, 0.2);
  transform:scale(1.02);
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
  margin-bottom: 0.5rem;
  border-bottom: 2px solid #eee;
  /* padding: 0.5rem; */
  font-size: 1.5rem;
  font-weight: bold;
}

h3 {
  color: #333;
  padding: 0.25rem 0;
  font-size: 1.2rem;
  font-weight: bold;
  margin-top: 1rem;
}

p {
    color: #333;
    padding:0.25rem 0.75rem;
}

.skills-grid {
  display: flex;
  justify-content: flex-end; 
  flex-wrap: wrap;
  gap: 0.5rem;
  margin-bottom: 1rem;
  margin-top: 0.75rem;
}

.skill-item {
  background: #f8f9fa;
  padding: 0.25rem;
  border-radius: 5px;
  text-align: center;
  font-size: 0.9rem;
  color: #555;
  border: 1px solid #eee;
  transition: ease-in-out 0.3s;
}

.skill-item:hover {
  background: #d4f9ff;
}

@media (max-width: 768px) {
  .profile-card {
    border-radius: 0;
  }

}
</style>