<template>
  <div class="home">
    <Header />
    
    <!-- 英雄区域 -->
    <section class="hero">
      <div class="hero-content">
        <h1 class="hero-title">欢迎来到我们的企业</h1>
        <p class="hero-subtitle">专业 · 创新 · 值得信赖</p>
        <el-button type="primary" size="large" @click="scrollToContent">
          了解更多
        </el-button>
      </div>
      <div class="hero-background"></div>
    </section>

    <!-- 特色服务 -->
    <section class="features" id="features">
      <div class="container">
        <h2 class="section-title">我们的优势</h2>
        <div class="features-grid">
          <el-card class="feature-card" shadow="hover">
            <el-icon class="feature-icon" :size="50"><Trophy /></el-icon>
            <h3>专业团队</h3>
            <p>拥有多年行业经验的专业团队，为您提供最优质的服务</p>
          </el-card>
          <el-card class="feature-card" shadow="hover">
            <el-icon class="feature-icon" :size="50"><Lightning /></el-icon>
            <h3>高效创新</h3>
            <p>持续创新，采用最新技术，确保高效交付</p>
          </el-card>
          <el-card class="feature-card" shadow="hover">
            <el-icon class="feature-icon" :size="50"><Lock /></el-icon>
            <h3>值得信赖</h3>
            <p>诚信经营，客户至上，值得您信赖的合作伙伴</p>
          </el-card>
        </div>
      </div>
    </section>

    <!-- 数据统计 -->
    <section class="stats">
      <div class="container">
        <div class="stats-grid">
          <div class="stat-item">
            <div class="stat-number">1000+</div>
            <div class="stat-label">满意客户</div>
          </div>
          <div class="stat-item">
            <div class="stat-number">500+</div>
            <div class="stat-label">成功项目</div>
          </div>
          <div class="stat-item">
            <div class="stat-number">10+</div>
            <div class="stat-label">年行业经验</div>
          </div>
          <div class="stat-item">
            <div class="stat-number">50+</div>
            <div class="stat-label">专业团队</div>
          </div>
        </div>
      </div>
    </section>

    <!-- 客户评价 -->
    <section class="testimonials">
      <div class="container">
        <h2 class="section-title">客户评价</h2>
        <div class="testimonials-grid">
          <el-card class="testimonial-card" shadow="hover">
            <div class="testimonial-content">
              <p>"非常专业的团队，服务态度好，项目交付及时，强烈推荐！"</p>
              <div class="testimonial-author">
                <strong>张先生</strong>
                <span>某科技公司 CEO</span>
              </div>
            </div>
          </el-card>
          <el-card class="testimonial-card" shadow="hover">
            <div class="testimonial-content">
              <p>"合作多年，一直很满意。他们的专业能力和服务态度都值得称赞。"</p>
              <div class="testimonial-author">
                <strong>李女士</strong>
                <span>某制造企业 总经理</span>
              </div>
            </div>
          </el-card>
          <el-card class="testimonial-card" shadow="hover">
            <div class="testimonial-content">
              <p>"响应速度快，解决方案专业，是我们值得信赖的合作伙伴。"</p>
              <div class="testimonial-author">
                <strong>王总</strong>
                <span>某贸易公司 董事长</span>
              </div>
            </div>
          </el-card>
        </div>
      </div>
    </section>

    <Footer />
  </div>
</template>

<script setup>
import { ref } from 'vue'
import Header from '../components/Header.vue'
import Footer from '../components/Footer.vue'
import { Trophy, Lightning, Lock } from '@element-plus/icons-vue'

const scrollToContent = () => {
  document.getElementById('features')?.scrollIntoView({ behavior: 'smooth' })
}
</script>

<style scoped>
.home {
  min-height: 100vh;
}

.hero {
  position: relative;
  height: 600px;
  display: flex;
  align-items: center;
  justify-content: center;
  overflow: hidden;
  color: #fff;
}

.hero-background {
  position: absolute;
  top: 0;
  left: 0;
  right: 0;
  bottom: 0;
  background: linear-gradient(135deg, #667eea 0%, #764ba2 100%);
  z-index: -1;
}

.hero-background::before {
  content: '';
  position: absolute;
  top: 0;
  left: 0;
  right: 0;
  bottom: 0;
  background: url('data:image/svg+xml,<svg width="100" height="100" xmlns="http://www.w3.org/2000/svg"><defs><pattern id="grid" width="100" height="100" patternUnits="userSpaceOnUse"><path d="M 100 0 L 0 0 0 100" fill="none" stroke="rgba(255,255,255,0.1)" stroke-width="1"/></pattern></defs><rect width="100" height="100" fill="url(%23grid)"/></svg>');
  opacity: 0.3;
}

.hero-content {
  text-align: center;
  z-index: 1;
  padding: 0 20px;
}

.hero-title {
  font-size: 48px;
  font-weight: 700;
  margin-bottom: 20px;
  animation: fadeInUp 1s ease;
}

.hero-subtitle {
  font-size: 24px;
  margin-bottom: 30px;
  opacity: 0.95;
  animation: fadeInUp 1s ease 0.2s both;
}

@keyframes fadeInUp {
  from {
    opacity: 0;
    transform: translateY(30px);
  }
  to {
    opacity: 1;
    transform: translateY(0);
  }
}

.container {
  max-width: 1200px;
  margin: 0 auto;
  padding: 80px 20px;
}

.section-title {
  text-align: center;
  font-size: 36px;
  font-weight: 600;
  margin-bottom: 50px;
  color: #2c3e50;
}

.features-grid {
  display: grid;
  grid-template-columns: repeat(auto-fit, minmax(300px, 1fr));
  gap: 30px;
}

.feature-card {
  text-align: center;
  padding: 40px 20px;
  transition: transform 0.3s;
}

.feature-card:hover {
  transform: translateY(-5px);
}

.feature-icon {
  color: #409eff;
  margin-bottom: 20px;
}

.feature-card h3 {
  font-size: 22px;
  margin-bottom: 15px;
  color: #2c3e50;
}

.feature-card p {
  color: #606266;
  line-height: 1.6;
}

.stats {
  background: linear-gradient(135deg, #667eea 0%, #764ba2 100%);
  color: #fff;
  padding: 60px 20px;
}

.stats-grid {
  display: grid;
  grid-template-columns: repeat(auto-fit, minmax(200px, 1fr));
  gap: 40px;
  text-align: center;
}

.stat-item {
  padding: 20px;
}

.stat-number {
  font-size: 48px;
  font-weight: 700;
  margin-bottom: 10px;
}

.stat-label {
  font-size: 18px;
  opacity: 0.9;
}

.testimonials {
  background: #f5f7fa;
  padding: 80px 20px;
}

.testimonials-grid {
  display: grid;
  grid-template-columns: repeat(auto-fit, minmax(300px, 1fr));
  gap: 30px;
}

.testimonial-card {
  padding: 30px;
}

.testimonial-content p {
  font-size: 16px;
  line-height: 1.8;
  color: #606266;
  margin-bottom: 20px;
  font-style: italic;
}

.testimonial-author {
  display: flex;
  flex-direction: column;
  gap: 5px;
}

.testimonial-author strong {
  color: #2c3e50;
  font-size: 16px;
}

.testimonial-author span {
  color: #909399;
  font-size: 14px;
}

@media (max-width: 768px) {
  .hero {
    height: 500px;
  }

  .hero-title {
    font-size: 32px;
  }

  .hero-subtitle {
    font-size: 18px;
  }

  .section-title {
    font-size: 28px;
  }

  .features-grid,
  .testimonials-grid {
    grid-template-columns: 1fr;
  }
}
</style>

