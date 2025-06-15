<template>
  <div class="interests-container">
    <div class="interests-wrapper">
      <button 
        class="scroll-button left" 
        @click="scrollLeft"
        v-show="canScrollLeft"
      >
        <svg viewBox="0 0 24 24" width="24" height="24">
          <path d="M15.41 7.41L14 6l-6 6 6 6 1.41-1.41L10.83 12z" fill="currentColor"/>
        </svg>
      </button>
      
      <div class="interests-scroll" ref="scrollContainer">
        <InterestCard
          v-for="interest in interests"
          :key="interest.id"
          :imageUrl="interest.imageUrl"
          :title="interest.title"
          :description="interest.description"
        />
      </div>

      <button 
        class="scroll-button right" 
        @click="scrollRight"
        v-show="canScrollRight"
      >
        <svg viewBox="0 0 24 24" width="24" height="24">
          <path d="M8.59 16.59L10 18l6-6-6-6-1.41 1.41L13.17 12z" fill="currentColor"/>
        </svg>
      </button>
    </div>
  </div>
</template>

<script>
import InterestCard from '@/components/InterestCard.vue'

export default {
  name: 'InterestList',
  components: {
    InterestCard
  },
  data() {
    return {
      interests: [
        {
          id: 1,
          imageUrl: '/intro/drawing.png',
          title: '繪畫',
          description: '水彩色鉛筆和數位繪圖是我常用的創作方式，雖然幾年前才從指繪改使用電繪板與繪圖軟體CSP創作，對CSP的功能沒有非常熟悉。'
        },
        {
          id: 2,
          imageUrl: '/intro/photo.jpg',
          title: '攝影',
          description: '一開始是為了練習構圖而開始接觸攝影，後來開始享受攝影風景、物件的樂趣'
        },
        {
          id: 3,
          imageUrl: '/intro/music.JPG',
          title: '音樂',
          description: '聽音樂是我生活中不可或缺的一部分，尤其鍾愛無損音樂帶來的細膩聽覺體驗。'
        },
        {
          id: 4,
          imageUrl: '/intro/bird.jpg',
          title: '賞鳥',
          description: '鳥類欣賞是我相當喜歡的戶外活動之一，拿著望遠鏡在家附近的田間小徑散步，有時會發現少見的令人驚喜的鳥種。'
        }
      ],
      canScrollLeft: false,
      canScrollRight: true
    }
  },
  mounted() {
    this.checkScroll();
    this.$refs.scrollContainer.addEventListener('scroll', this.checkScroll);
  },
  beforeUnmount() {
    this.$refs.scrollContainer.removeEventListener('scroll', this.checkScroll);
  },
  methods: {
    checkScroll() {
      const container = this.$refs.scrollContainer;
      this.canScrollLeft = container.scrollLeft > 0;
      this.canScrollRight = container.scrollLeft < (container.scrollWidth - container.clientWidth);
    },
    scrollLeft() {
      const container = this.$refs.scrollContainer;
      container.scrollBy({ left: -340, behavior: 'smooth' });
    },
    scrollRight() {
      const container = this.$refs.scrollContainer;
      container.scrollBy({ left: 340, behavior: 'smooth' });
    }
  }
}
</script>

<style scoped>
.interests-container {
  padding: 0px 5px;
}

.interests-wrapper {
  position: relative;
  display: flex;
  align-items: center;
}

.interests-scroll {
  display: flex;
  overflow-x: auto;
  padding: 1rem 0;
  scroll-behavior: smooth;
  -webkit-overflow-scrolling: touch;
  scrollbar-width: none; /* Firefox */
  -ms-overflow-style: none; /* IE and Edge */
}

.interests-scroll::-webkit-scrollbar {
  display: none; /* Chrome, Safari and Opera */
}

.scroll-button {
  position: absolute;
  width: 40px;
  height: 40px;
  border-radius: 50%;
  background: white;
  border: none;
  box-shadow: 0 2px 6px rgba(0, 0, 0, 0.2);
  cursor: pointer;
  display: flex;
  align-items: center;
  justify-content: center;
  z-index: 1;
  transition: all 0.3s ease;
}

.scroll-button:hover {
  background: #f0f0f0;
  box-shadow: 0 4px 8px rgba(0, 0, 0, 0.2);
}

.scroll-button.left {
  left: -20px;
}

.scroll-button.right {
  right: -20px;
}

.scroll-button i {
  color: #333;
  font-size: 1rem;
}

/* 確保卡片容器有足夠的間距以顯示箭頭 */
.interests-scroll {
  margin: 0 30px;
}
</style>