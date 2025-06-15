<template>
  <div class="interest-card">
    <div class="card-image">
      <img :src="imageUrl" :alt="title">
    </div>
    <div class="card-content">
      <h3>{{ title }}</h3>
      <p>{{ description }}</p>
    </div>
  </div>
</template>

<script>
// 確保只有一個 export default
export default {
  name: 'InterestCard',
  props: {
    imageUrl: {
      type: String,
      required: true
    },
    title: {
      type: String,
      required: true
    },
    description: {
      type: String,
      required: true
    }
  }
}
</script>
<style scoped>
    .interest-card {
    min-width: 300px;
    max-width: 300px;
    background: white;
    border-radius: 12px;
    box-shadow: 0 2px 8px rgba(0, 0, 0, 0.1);
    margin: 10px;
    transition: transform 0.3s ease;
    }

    .interest-card:hover {
    transform: translateY(-5px);
    }

    .card-image {
    height: 200px;  /* 修改這裡，將高度設為 200px */
    max-height: 300px;  /* 添加這行，確保不超過 300px */
    overflow: hidden;
    border-radius: 12px 12px 0 0;
    }

    .card-image img {
    width: 100%;
    height: 100%;
    object-fit: cover;  /* 確保圖片覆蓋整個容器且不變形 */
    }

    .card-content {
        padding: 0px 10px;
        margin: 10px;
    }
    h3 {
      margin: 10px 0px;
      font-size: 1.2rem;
      font-weight: bolder;
      color: #333;
      margin-bottom: 1rem;
      border-bottom: 2px solid #eee;
      padding-bottom: 0.5rem;
    }
</style>