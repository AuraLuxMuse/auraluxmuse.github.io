<script>
export default {
  data() {
    return {
      imagePath: 'teaser.png'  // 替换为你自己的图片路径
    }
  }
}
</script>

<template>
  <div>
    <el-divider />

    <el-row justify="center">
      <h1 class="section-title">Teaser Figure</h1>
    </el-row>

    <!-- 插入图片 -->
    <el-row justify="center">
      <el-col :xs="24" :sm="20" :md="16" :lg="12" :xl="12">
        <img :src="imagePath" class="chart-image" alt="Quantitative Results" />
      </el-col>
    </el-row>
  </div>
</template>

<style scoped>
.chart-image {
  width: 100%;
  height: auto;
  margin-top: 20px;
  object-fit: contain;
}
</style>