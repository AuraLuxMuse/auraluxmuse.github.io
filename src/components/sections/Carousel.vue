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

    <!-- Insert image and paragraph -->
    <el-row justify="center">
      <el-col :xs="24" :sm="20" :md="16" :lg="12" :xl="12">
        <img :src="imagePath" class="chart-image" alt="Quantitative Results" />
        <p class="image-description">
          In the conventional pipeline,
designers manually decompose the input music into artistic components, followed by iterative design, precise time alignment and parameter input into the
lighting console. In contrast, AuraLuxMuse automates this process by leveraging deep audio feature extraction and contrastive representation learning. The
system guides the generation of lighting parameters, which are seamlessly delivered to the console for real-time aesthetic lighting production.
        </p>
      </el-col>
    </el-row>

  </div>
</template>

<style scoped>

.image-description {
  text-indent: 32px;
  font-family: "Helvetica Neue", Arial, -apple-system, BlinkMacSystemFont, "Segoe UI", Roboto, Oxygen, Ubuntu, Cantarell, "Open Sans", sans-serif;
  font-size: 16px;
  color: #000;
  line-height: 1.6; /* Adjusted from 1 to 1.6 for better readability */
  text-align: justify;
}

.chart-image {
  width: 100%;
  height: auto;
  margin-top: 20px;
  object-fit: contain;
}
</style>