<template>
  <el-footer class="footer">
    <div class="footer-container">
      <div class="footer-content">
        <div class="footer-section">
          <h3>企业品牌</h3>
          <p>致力于为客户提供优质的产品和服务</p>
        </div>
        <div class="footer-section">
          <h4>快速链接</h4>
          <ul>
            <li><router-link to="/">首页</router-link></li>
            <li><router-link to="/about">关于我们</router-link></li>
            <li><router-link to="/products">产品服务</router-link></li>
            <li><router-link to="/contact">联系我们</router-link></li>
          </ul>
        </div>
        <div class="footer-section">
          <h4>联系方式</h4>
          <p>电话：400-123-4567</p>
          <p>邮箱：info@company.com</p>
          <p>地址：中国·北京</p>
        </div>
      </div>
      <div class="footer-bottom">
        <p>&copy; 2024 企业品牌. 保留所有权利.</p>
      </div>
    </div>
  </el-footer>
</template>

<script setup>
</script>

<style scoped>
.footer {
    height:360px;
    background: linear-gradient(135deg, #667eea 0%, #764ba2 100%);
    color: #fff;
    padding: 60px 0 20px;
    margin-top: 80px;
    width: 100%;
}

.footer-container {
  max-width: 1200px;
  margin: 0 auto;
  padding: 0 20px;
}

.footer-content {
  display: grid;
  grid-template-columns: 2fr 1.5fr 1.5fr;
  gap: 60px;
  margin-bottom: 40px;
}

.footer-section {
  display: flex;
  flex-direction: column;
}

.footer-section:first-child {
  max-width: 350px;
}

.footer-section h3 {
  font-size: 26px;
  margin-bottom: 20px;
  font-weight: 700;
  letter-spacing: 0.5px;
}

.footer-section h4 {
  font-size: 18px;
  margin-bottom: 20px;
  font-weight: 600;
  letter-spacing: 0.3px;
}

.footer-section p {
  margin: 10px 0;
  opacity: 0.95;
  line-height: 1.8;
  font-size: 15px;
}

.footer-section:first-child p {
  font-size: 15px;
  line-height: 1.8;
  opacity: 0.9;
}

.footer-section ul {
  list-style: none;
  padding: 0;
  margin: 0;
}

.footer-section ul li {
  margin: 12px 0;
}

.footer-section ul li a {
  color: #fff;
  text-decoration: none;
  opacity: 0.9;
  transition: all 0.3s ease;
  font-size: 15px;
  display: inline-block;
  position: relative;
  padding-left: 0;
}

.footer-section ul li a::before {
  content: '→';
  margin-right: 8px;
  opacity: 0;
  transition: all 0.3s ease;
  position: absolute;
  left: -15px;
}

.footer-section ul li a:hover {
  opacity: 1;
  padding-left: 15px;
}

.footer-section ul li a:hover::before {
  opacity: 1;
  left: 0;
}

.footer-bottom {
  text-align: center;
  padding-top: 30px;
  border-top: 1px solid rgba(255, 255, 255, 0.25);
  margin-top: 20px;
}

.footer-bottom p {
  margin: 0;
  opacity: 0.85;
  font-size: 14px;
  letter-spacing: 0.5px;
}

@media (max-width: 968px) {
  .footer-content {
    grid-template-columns: 1fr 1fr;
    gap: 40px;
  }

  .footer-section:first-child {
    grid-column: 1 / -1;
    max-width: 100%;
  }
}

@media (max-width: 768px) {
  .footer {
    padding: 50px 0 20px;
  }

  .footer-content {
    grid-template-columns: 1fr;
    gap: 35px;
  }

  .footer-section:first-child {
    grid-column: 1;
  }

  .footer-section h3 {
    font-size: 22px;
  }

  .footer-section h4 {
    font-size: 17px;
  }

  .footer-section p,
  .footer-section ul li a {
    font-size: 14px;
  }
}
</style>

