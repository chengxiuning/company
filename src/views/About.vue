<template>
  <div class="about">
    <Header />
    
    <!-- 关于我们横幅 -->
    <section class="banner">
      <div class="banner-content">
        <h1>关于我们</h1>
        <p>了解我们的故事、使命和愿景</p>
      </div>
    </section>

    <!-- 公司介绍 -->
    <section class="intro">
      <div class="container">
        <div class="intro-content">
          <div class="intro-text">
            <h2>我们的故事</h2>
            <p>
              我们是一家专注于为客户提供优质产品和服务的企业。自成立以来，我们始终坚持以客户为中心，
              以创新为驱动，以质量为生命，赢得了广大客户的信赖和支持。
            </p>
            <p>
              经过多年的发展，我们已经成长为行业内的领先企业，拥有专业的团队、先进的技术和完善的服务体系。
              我们致力于为客户创造更大的价值，推动行业的持续发展。
            </p>
          </div>
          <div class="intro-image">
            <el-image
              src="https://via.placeholder.com/500x400/667eea/ffffff?text=企业形象"
              fit="cover"
              class="image-placeholder"
            />
          </div>
        </div>
      </div>
    </section>

    <!-- 使命愿景 -->
    <section class="mission-vision">
      <div class="container">
        <div class="mv-grid">
          <el-card class="mv-card" shadow="hover">
            <el-icon class="mv-icon" :size="60"><Aim /></el-icon>
            <h3>我们的使命</h3>
            <p>
              为客户提供最优质的产品和服务，创造更大的价值，
              成为客户最值得信赖的合作伙伴。
            </p>
          </el-card>
          <el-card class="mv-card" shadow="hover">
            <el-icon class="mv-icon" :size="60"><View /></el-icon>
            <h3>我们的愿景</h3>
            <p>
              成为行业内的领军企业，引领行业发展方向，
              为社会的进步和发展做出贡献。
            </p>
          </el-card>
        </div>
      </div>
    </section>

    <!-- 核心价值观 -->
    <section class="values">
      <div class="container">
        <h2 class="section-title">核心价值观</h2>
        <div class="values-grid">
          <div class="value-item">
            <el-icon class="value-icon" :size="40"><Star /></el-icon>
            <h4>诚信</h4>
            <p>诚实守信，言行一致</p>
          </div>
          <div class="value-item">
            <el-icon class="value-icon" :size="40"><Trophy /></el-icon>
            <h4>专业</h4>
            <p>专业能力，精益求精</p>
          </div>
          <div class="value-item">
            <el-icon class="value-icon" :size="40"><Connection /></el-icon>
            <h4>合作</h4>
            <p>团队协作，共同成长</p>
          </div>
          <div class="value-item">
            <el-icon class="value-icon" :size="40"><Lightning /></el-icon>
            <h4>创新</h4>
            <p>持续创新，追求卓越</p>
          </div>
        </div>
      </div>
    </section>

    <!-- 发展历程 -->
    <section class="timeline-section">
      <div class="container">
        <h2 class="section-title">发展历程</h2>
        <el-timeline>
          <el-timeline-item timestamp="2024" placement="top">
            <el-card>
              <h4>持续创新</h4>
              <p>推出新产品线，扩大市场份额</p>
            </el-card>
          </el-timeline-item>
          <el-timeline-item timestamp="2020" placement="top">
            <el-card>
              <h4>快速发展</h4>
              <p>业务规模扩大，团队人数翻倍</p>
            </el-card>
          </el-timeline-item>
          <el-timeline-item timestamp="2015" placement="top">
            <el-card>
              <h4>稳步成长</h4>
              <p>建立完善的服务体系，获得行业认可</p>
            </el-card>
          </el-timeline-item>
          <el-timeline-item timestamp="2010" placement="top">
            <el-card>
              <h4>公司成立</h4>
              <p>正式成立，开始为客户提供服务</p>
            </el-card>
          </el-timeline-item>
        </el-timeline>
      </div>
    </section>

    <Footer />
  </div>
</template>

<script setup>
import Header from '../components/Header.vue'
import Footer from '../components/Footer.vue'
import { Aim, View, Star, Trophy, Connection, Lightning } from '@element-plus/icons-vue'
</script>

<style scoped>
.about {
  min-height: 100vh;
}

.banner {
  background: linear-gradient(135deg, #667eea 0%, #764ba2 100%);
  color: #fff;
  padding: 100px 20px;
  text-align: center;
}

.banner-content h1 {
  font-size: 48px;
  font-weight: 700;
  margin-bottom: 20px;
}

.banner-content p {
  font-size: 20px;
  opacity: 0.95;
}

.container {
  max-width: 1200px;
  margin: 0 auto;
  padding: 80px 20px;
}

.intro {
  padding: 80px 20px;
}

.intro-content {
  display: grid;
  grid-template-columns: 1fr 1fr;
  gap: 60px;
  align-items: center;
}

.intro-text h2 {
  font-size: 36px;
  margin-bottom: 30px;
  color: #2c3e50;
}

.intro-text p {
  font-size: 16px;
  line-height: 1.8;
  color: #606266;
  margin-bottom: 20px;
}

.intro-image {
  border-radius: 8px;
  overflow: hidden;
}

.image-placeholder {
  width: 100%;
  height: 400px;
  border-radius: 8px;
}

.mission-vision {
  background: #f5f7fa;
  padding: 80px 20px;
}

.mv-grid {
  display: grid;
  grid-template-columns: repeat(auto-fit, minmax(400px, 1fr));
  gap: 40px;
}

.mv-card {
  text-align: center;
  padding: 50px 30px;
}

.mv-icon {
  color: #409eff;
  margin-bottom: 20px;
}

.mv-card h3 {
  font-size: 24px;
  margin-bottom: 20px;
  color: #2c3e50;
}

.mv-card p {
  font-size: 16px;
  line-height: 1.8;
  color: #606266;
}

.values {
  padding: 80px 20px;
}

.section-title {
  text-align: center;
  font-size: 36px;
  font-weight: 600;
  margin-bottom: 50px;
  color: #2c3e50;
}

.values-grid {
  display: grid;
  grid-template-columns: repeat(auto-fit, minmax(250px, 1fr));
  gap: 40px;
}

.value-item {
  text-align: center;
  padding: 30px;
}

.value-icon {
  color: #409eff;
  margin-bottom: 20px;
}

.value-item h4 {
  font-size: 20px;
  margin-bottom: 15px;
  color: #2c3e50;
}

.value-item p {
  color: #606266;
  line-height: 1.6;
}

.timeline-section {
  background: #f5f7fa;
  padding: 80px 20px;
}

:deep(.el-timeline-item__timestamp) {
  font-size: 18px;
  font-weight: 600;
  color: #409eff;
}

:deep(.el-timeline-item__content h4) {
  font-size: 20px;
  margin-bottom: 10px;
  color: #2c3e50;
}

:deep(.el-timeline-item__content p) {
  color: #606266;
  line-height: 1.6;
}

@media (max-width: 768px) {
  .banner-content h1 {
    font-size: 32px;
  }

  .intro-content {
    grid-template-columns: 1fr;
    gap: 40px;
  }

  .mv-grid {
    grid-template-columns: 1fr;
  }

  .values-grid {
    grid-template-columns: repeat(2, 1fr);
  }
}
</style>

