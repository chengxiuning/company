<template>
  <div class="contact">
    <Header />
    
    <!-- 联系横幅 -->
    <section class="banner">
      <div class="banner-content">
        <h1>联系我们</h1>
        <p>我们期待与您的合作</p>
      </div>
    </section>

    <!-- 联系表单和信息 -->
    <section class="contact-section">
      <div class="container">
        <div class="contact-content">
          <!-- 联系表单 -->
          <div class="contact-form-wrapper">
            <h2>发送消息</h2>
            <el-form
              ref="formRef"
              :model="form"
              :rules="rules"
              label-width="80px"
              class="contact-form"
            >
              <el-form-item label="姓名" prop="name">
                <el-input v-model="form.name" placeholder="请输入您的姓名" />
              </el-form-item>
              <el-form-item label="邮箱" prop="email">
                <el-input v-model="form.email" placeholder="请输入您的邮箱" />
              </el-form-item>
              <el-form-item label="电话" prop="phone">
                <el-input v-model="form.phone" placeholder="请输入您的电话" />
              </el-form-item>
              <el-form-item label="主题" prop="subject">
                <el-input v-model="form.subject" placeholder="请输入主题" />
              </el-form-item>
              <el-form-item label="消息" prop="message">
                <el-input
                  v-model="form.message"
                  type="textarea"
                  :rows="6"
                  placeholder="请输入您的消息"
                />
              </el-form-item>
              <el-form-item>
                <el-button type="primary" size="large" @click="submitForm" :loading="submitting">
                  提交
                </el-button>
                <el-button size="large" @click="resetForm">重置</el-button>
              </el-form-item>
            </el-form>
          </div>

          <!-- 联系信息 -->
          <div class="contact-info-wrapper">
            <h2>联系方式</h2>
            <div class="contact-info">
              <div class="info-item">
                <el-icon class="info-icon" :size="30"><Location /></el-icon>
                <div class="info-content">
                  <h4>地址</h4>
                  <p>中国·北京市朝阳区</p>
                  <p>某某大厦 10 层</p>
                </div>
              </div>
              <div class="info-item">
                <el-icon class="info-icon" :size="30"><Phone /></el-icon>
                <div class="info-content">
                  <h4>电话</h4>
                  <p>400-123-4567</p>
                  <p>010-12345678</p>
                </div>
              </div>
              <div class="info-item">
                <el-icon class="info-icon" :size="30"><Message /></el-icon>
                <div class="info-content">
                  <h4>邮箱</h4>
                  <p>info@company.com</p>
                  <p>contact@company.com</p>
                </div>
              </div>
              <div class="info-item">
                <el-icon class="info-icon" :size="30"><Clock /></el-icon>
                <div class="info-content">
                  <h4>工作时间</h4>
                  <p>周一至周五：9:00 - 18:00</p>
                  <p>周六：9:00 - 12:00</p>
                </div>
              </div>
            </div>

            <!-- 地图占位 -->
            <div class="map-placeholder">
              <el-image
                src="https://via.placeholder.com/500x300/667eea/ffffff?text=地图位置"
                fit="cover"
                class="map-image"
              />
            </div>
          </div>
        </div>
      </div>
    </section>

    <Footer />
  </div>
</template>

<script setup>
import { ref, reactive } from 'vue'
import { ElMessage } from 'element-plus'
import Header from '../components/Header.vue'
import Footer from '../components/Footer.vue'
import { Location, Phone, Message, Clock } from '@element-plus/icons-vue'

const formRef = ref(null)
const submitting = ref(false)

const form = reactive({
  name: '',
  email: '',
  phone: '',
  subject: '',
  message: ''
})

const rules = {
  name: [
    { required: true, message: '请输入姓名', trigger: 'blur' }
  ],
  email: [
    { required: true, message: '请输入邮箱', trigger: 'blur' },
    { type: 'email', message: '请输入正确的邮箱格式', trigger: 'blur' }
  ],
  phone: [
    { required: true, message: '请输入电话', trigger: 'blur' },
    { pattern: /^1[3-9]\d{9}$/, message: '请输入正确的手机号码', trigger: 'blur' }
  ],
  subject: [
    { required: true, message: '请输入主题', trigger: 'blur' }
  ],
  message: [
    { required: true, message: '请输入消息内容', trigger: 'blur' },
    { min: 10, message: '消息内容至少10个字符', trigger: 'blur' }
  ]
}

const submitForm = async () => {
  if (!formRef.value) return
  
  try {
    await formRef.value.validate()
    submitting.value = true
    
    // 模拟提交
    setTimeout(() => {
      submitting.value = false
      ElMessage.success('消息发送成功！我们会尽快与您联系。')
      resetForm()
    }, 1500)
  } catch (error) {
    console.log('表单验证失败', error)
  }
}

const resetForm = () => {
  if (!formRef.value) return
  formRef.value.resetFields()
}
</script>

<style scoped>
.contact {
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

.contact-content {
  display: grid;
  grid-template-columns: 1fr 1fr;
  gap: 60px;
  align-items: start;
}

.contact-form-wrapper h2,
.contact-info-wrapper h2 {
  font-size: 28px;
  margin-bottom: 30px;
  color: #2c3e50;
}

.contact-form {
  background: #fff;
  padding: 30px;
  border-radius: 8px;
  box-shadow: 0 2px 12px 0 rgba(0, 0, 0, 0.1);
}

.contact-info {
  margin-bottom: 40px;
}

.info-item {
  display: flex;
  align-items: flex-start;
  margin-bottom: 30px;
  padding: 20px;
  background: #f5f7fa;
  border-radius: 8px;
  transition: transform 0.3s;
}

.info-item:hover {
  transform: translateX(5px);
}

.info-icon {
  color: #409eff;
  margin-right: 20px;
  flex-shrink: 0;
}

.info-content h4 {
  font-size: 18px;
  margin-bottom: 10px;
  color: #2c3e50;
}

.info-content p {
  color: #606266;
  line-height: 1.8;
  margin: 5px 0;
}

.map-placeholder {
  border-radius: 8px;
  overflow: hidden;
  box-shadow: 0 2px 12px 0 rgba(0, 0, 0, 0.1);
}

.map-image {
  width: 100%;
  height: 300px;
  border-radius: 8px;
}

@media (max-width: 968px) {
  .contact-content {
    grid-template-columns: 1fr;
    gap: 40px;
  }
}

@media (max-width: 768px) {
  .banner-content h1 {
    font-size: 32px;
  }

  .contact-form {
    padding: 20px;
  }
}
</style>

