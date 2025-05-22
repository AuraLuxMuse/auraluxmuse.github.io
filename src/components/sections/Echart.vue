<script>
export default {
  data() {
    return {
      imagePath: 'dataset_procedure.png'  // 替换为你自己的图片路径
    }
  }
}
</script>

<template>
  <div>
    <el-divider />

    <el-row justify="center">
      <h1 class="section-title">Dataset: Musilux Construction Procedure</h1>
    </el-row>

    <!-- 插入图片和标题 -->
    <el-row justify="center">
      <el-col :xs="24" :sm="20" :md="16" :lg="12" :xl="12">
        <figure>
          <img :src="imagePath" class="chart-image" alt="Quantitative Results" />
          <figcaption class="image-caption">
            Initially, music and lighting cues are collected, and the distribution across scenarios is shown in the collection procedure. Alignment is performed at both the internal level of cues and the cross-modal level to synchronize music and lighting data. The resulting aligned sequences are then aggregated into Cue Sequence Corpus, constituting our Musilux Dataset.
          </figcaption>
        </figure>
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

.image-caption {
  font-size: 14px;
  color: #666;
  margin-top: 10px;
  line-height: 1.5;
}
</style>