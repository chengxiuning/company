<template>
  <div class="products">
    <Header />
    
    <!-- 产品横幅 -->
    <section class="banner">
      <div class="banner-content">
        <h1>产品与服务</h1>
        <p>为您提供全方位的解决方案</p>
      </div>
    </section>

    <!-- 产品列表 -->
    <section class="products-section">
      <div class="container">
        <div class="products-grid">
          <el-card
            v-for="product in products"
            :key="product.id"
            class="product-card"
            shadow="hover"
            @click="viewProduct(product)"
          >
            <el-image
              :src="product.image"
              fit="cover"
              class="product-image"
            />
            <div class="product-content">
              <h3>{{ product.name }}</h3>
              <p>{{ product.description }}</p>
              <div class="product-features">
                <el-tag
                  v-for="feature in product.features"
                  :key="feature"
                  class="feature-tag"
                >
                  {{ feature }}
                </el-tag>
              </div>
              <el-button type="primary" class="product-btn">
                了解更多
              </el-button>
            </div>
          </el-card>
        </div>
      </div>
    </section>

    <!-- 服务流程 -->
    <section class="process-section">
      <div class="container">
        <h2 class="section-title">服务流程</h2>
        <div class="process-steps">
          <div
            v-for="(step, index) in processSteps"
            :key="index"
            class="process-step"
          >
            <div class="step-number">{{ index + 1 }}</div>
            <el-icon class="step-icon" :size="40">
              <component :is="step.icon" />
            </el-icon>
            <h4>{{ step.title }}</h4>
            <p>{{ step.description }}</p>
          </div>
        </div>
      </div>
    </section>

    <!-- 服务优势 -->
    <section class="advantages-section">
      <div class="container">
        <h2 class="section-title">服务优势</h2>
        <div class="advantages-grid">
          <div
            v-for="advantage in advantages"
            :key="advantage.id"
            class="advantage-item"
          >
            <el-icon class="advantage-icon" :size="50">
              <component :is="advantage.icon" />
            </el-icon>
            <h4>{{ advantage.title }}</h4>
            <p>{{ advantage.description }}</p>
          </div>
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
import {
  Document,
  ChatLineRound,
  Setting,
  Checked,
  Timer,
  Service,
  Tools,
  User
} from '@element-plus/icons-vue'

const products = ref([
  {
    id: 1,
    name: '产品方案 A',
    description: '专业的解决方案，满足您的核心业务需求，提供全方位的技术支持。',
    image: 'https://via.placeholder.com/400x300/667eea/ffffff?text=产品A',
    features: ['高效', '稳定', '安全']
  },
  {
    id: 2,
    name: '产品方案 B',
    description: '创新的技术方案，帮助您提升业务效率，实现数字化转型。',
    image: 'https://via.placeholder.com/400x300/764ba2/ffffff?text=产品B',
    features: ['创新', '智能', '便捷']
  },
  {
    id: 3,
    name: '产品方案 C',
    description: '定制化的服务方案，根据您的具体需求提供个性化解决方案。',
    image: 'https://via.placeholder.com/400x300/f093fb/ffffff?text=产品C',
    features: ['定制', '专业', '贴心']
  },
  {
    id: 4,
    name: '产品方案 D',
    description: '全面的服务支持，从咨询到实施，全程陪伴您的业务发展。',
    image: 'https://via.placeholder.com/400x300/4facfe/ffffff?text=产品D',
    features: ['全面', '可靠', '持续']
  }
])

const processSteps = [
  {
    icon: 'Document',
    title: '需求分析',
    description: '深入了解您的业务需求，制定专业的解决方案'
  },
  {
    icon: 'ChatLineRound',
    title: '方案设计',
    description: '根据需求设计最优方案，确保方案的可行性和有效性'
  },
  {
    icon: 'Setting',
    title: '实施部署',
    description: '专业团队负责实施，确保项目按时高质量交付'
  },
  {
    icon: 'Checked',
    title: '持续支持',
    description: '提供长期的技术支持和维护服务，保障系统稳定运行'
  }
]

const advantages = [
  {
    id: 1,
    icon: 'Timer',
    title: '快速响应',
    description: '7x24小时技术支持，快速响应客户需求'
  },
  {
    id: 2,
    icon: 'Service',
    title: '专业服务',
    description: '经验丰富的专业团队，提供优质服务'
  },
  {
    id: 3,
    icon: 'Tools',
    title: '技术先进',
    description: '采用最新技术，确保解决方案的先进性'
  },
  {
    id: 4,
    icon: 'User',
    title: '客户至上',
    description: '以客户为中心，提供个性化的服务体验'
  }
]

const viewProduct = (product) => {
  // 可以跳转到产品详情页或显示详情对话框
  console.log('查看产品:', product.name)
}
</script>

<style scoped>
.products {
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

.products-grid {
  display: grid;
  grid-template-columns: repeat(auto-fit, minmax(300px, 1fr));
  gap: 30px;
}

.product-card {
  cursor: pointer;
  transition: transform 0.3s;
  overflow: hidden;
}

.product-card:hover {
  transform: translateY(-5px);
}

.product-image {
  width: 100%;
  height: 200px;
  border-radius: 4px 4px 0 0;
}

.product-content {
  padding: 20px;
}

.product-content h3 {
  font-size: 22px;
  margin-bottom: 15px;
  color: #2c3e50;
}

.product-content p {
  color: #606266;
  line-height: 1.6;
  margin-bottom: 15px;
}

.product-features {
  display: flex;
  flex-wrap: wrap;
  gap: 10px;
  margin-bottom: 20px;
}

.feature-tag {
  margin: 0;
}

.product-btn {
  width: 100%;
}

.process-section {
  background: #f5f7fa;
  padding: 80px 20px;
}

.section-title {
  text-align: center;
  font-size: 36px;
  font-weight: 600;
  margin-bottom: 50px;
  color: #2c3e50;
}

.process-steps {
  display: grid;
  grid-template-columns: repeat(auto-fit, minmax(250px, 1fr));
  gap: 40px;
  position: relative;
}

.process-step {
  text-align: center;
  position: relative;
  padding: 30px 20px;
}

.step-number {
  position: absolute;
  top: -10px;
  left: 50%;
  transform: translateX(-50%);
  width: 40px;
  height: 40px;
  background: #409eff;
  color: #fff;
  border-radius: 50%;
  display: flex;
  align-items: center;
  justify-content: center;
  font-weight: 600;
  font-size: 18px;
}

.step-icon {
  color: #409eff;
  margin: 20px 0 15px;
}

.process-step h4 {
  font-size: 20px;
  margin-bottom: 15px;
  color: #2c3e50;
}

.process-step p {
  color: #606266;
  line-height: 1.6;
}

.advantages-section {
  padding: 80px 20px;
}

.advantages-grid {
  display: grid;
  grid-template-columns: repeat(auto-fit, minmax(250px, 1fr));
  gap: 40px;
}

.advantage-item {
  text-align: center;
  padding: 30px;
}

.advantage-icon {
  color: #409eff;
  margin-bottom: 20px;
}

.advantage-item h4 {
  font-size: 20px;
  margin-bottom: 15px;
  color: #2c3e50;
}

.advantage-item p {
  color: #606266;
  line-height: 1.6;
}

@media (max-width: 768px) {
  .banner-content h1 {
    font-size: 32px;
  }

  .products-grid {
    grid-template-columns: 1fr;
  }

  .process-steps {
    grid-template-columns: 1fr;
  }

  .advantages-grid {
    grid-template-columns: repeat(2, 1fr);
  }
}
</style>

