<template>
  <div class="about-container">
    <div class="profile-card">
      <div class="profile-header">
        <div class="profile-image">
          <img src="/intro/pic.png" alt="Profile Photo">
        </div>
        <h1 class="text-4xl font-bold mb-4 text-white-800">林敬玲</h1>
        <a href="mailto:home319148195@gmail.com">home319148195@gmail.com</a>
      </div>
      
      <div class="profile-content">
        <section class="about-section">
          <h2>About Me</h2>
          <p>一個會因為好奇而到處學習的好奇人</p>
        </section>

        <section class="skills-section">
          <h2>Skills</h2>
          <div class="skills-grid">
            <div class="skill-item">Nuxt 3</div>
            <div class="skill-item">Vue.js</div>
            <div class="skill-item">matlab</div>
            <div class="skill-item">python</div>
            <div class="skill-item">verilog</div>
          </div>
        </section>
        
        <h2>Interests</h2>
        <InterestList />

        <section class="contact-section">
          <h2>Contact</h2>
          <div class="contact-links">
            
            <a href="https://github.com/yourusername"><i class="fab fa-github"></i> GitHub</a>
            <a href="https://linkedin.com/in/yourusername"><i class="fab fa-linkedin"></i> LinkedIn</a>
          </div>
        </section>
      </div>
    </div>
  </div>
</template>

<script>
    import InterestList from '@/components/InterestList.vue'

    export default {
        name: 'AboutMe',
        components: {
            InterestList
        }
    }
</script>

<style scoped>
.about-container {
  min-height: 100vh; /* 確保最小高度為視窗高度 */
  width: 100%;
  display: flex;
  justify-content: center;
  align-items: flex-start; /* 改為頂部對齊 */
  padding: 2rem;
  box-sizing: border-box; /* 確保 padding 不會增加容器大小 */
}

.profile-card {
  max-width: 800px;
  width: 100%;
  background: white;
  border-radius: 15px;
  box-shadow: 0 4px 6px rgba(0, 0, 0, 0.1);
  overflow: hidden;
}

.profile-header {
  text-align: center;
  padding: 2rem;
  background-color: #B6FDFF;
  background-image: url("data:image/svg+xml,%3Csvg xmlns='http://www.w3.org/2000/svg' width='100%25' height='100%25' viewBox='0 0 1600 800'%3E%3Cg stroke='%23040515' stroke-width='71.4' stroke-opacity='0.19' %3E%3Ccircle fill='%23B6FDFF' cx='0' cy='0' r='1800'/%3E%3Ccircle fill='%23adf0f5' cx='0' cy='0' r='1700'/%3E%3Ccircle fill='%23a3e2eb' cx='0' cy='0' r='1600'/%3E%3Ccircle fill='%239ad5e1' cx='0' cy='0' r='1500'/%3E%3Ccircle fill='%2390c7d7' cx='0' cy='0' r='1400'/%3E%3Ccircle fill='%2387bacd' cx='0' cy='0' r='1300'/%3E%3Ccircle fill='%237dacc3' cx='0' cy='0' r='1200'/%3E%3Ccircle fill='%23749fb9' cx='0' cy='0' r='1100'/%3E%3Ccircle fill='%236a91af' cx='0' cy='0' r='1000'/%3E%3Ccircle fill='%236184a5' cx='0' cy='0' r='900'/%3E%3Ccircle fill='%2357769b' cx='0' cy='0' r='800'/%3E%3Ccircle fill='%234e6991' cx='0' cy='0' r='700'/%3E%3Ccircle fill='%23445b87' cx='0' cy='0' r='600'/%3E%3Ccircle fill='%233b4e7d' cx='0' cy='0' r='500'/%3E%3Ccircle fill='%23314073' cx='0' cy='0' r='400'/%3E%3Ccircle fill='%23283369' cx='0' cy='0' r='300'/%3E%3Ccircle fill='%231e255f' cx='0' cy='0' r='200'/%3E%3Ccircle fill='%23151855' cx='0' cy='0' r='100'/%3E%3C/g%3E%3C/svg%3E");
  background-attachment: fixed;
  background-size: cover;
  color: white;
}

.profile-image {
  width: 150px;
  height: 150px;
  margin: 0 auto 1rem;
  border-radius: 50%;
  overflow: hidden;
  border: 4px solid white;
}

.profile-image img {
  width: 100%;
  height: 100%;
  object-fit: cover;
}

.title {
  font-size: 1.2rem;
  opacity: 0.9;
}

.profile-content {
  padding: 2rem;
}

section {
  margin-bottom: 2rem;
}

h1 {
  padding-bottom: 1rem;
}

h2 {
  color: #333;
  margin-bottom: 1rem;
  border-bottom: 2px solid #eee;
  padding-bottom: 0.5rem;
  font-size: 1.5rem;
  font-weight: bold;
}

.skills-grid {
  display: grid;
  grid-template-columns: repeat(auto-fill, minmax(120px, 1fr));
  gap: 1rem;
}

.skill-item {
  background: #f8f9fa;
  padding: 0.8rem;
  border-radius: 8px;
  text-align: center;
  font-size: 0.9rem;
  color: #555;
  border: 1px solid #eee;
}

.contact-links {
  display: flex;
  gap: 1.5rem;
  justify-content: center;
}

.contact-links a {
  color: #555;
  text-decoration: none;
  display: flex;
  align-items: center;
  gap: 0.5rem;
  transition: color 0.3s;
}

.contact-links a:hover {
  color: #667eea;
}

@media (max-width: 768px) {
  .profile-card {
    border-radius: 0;
  }
  
  .contact-links {
    flex-direction: column;
    align-items: center;
  }
}
</style>