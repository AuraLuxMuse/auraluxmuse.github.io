<script>
export default {
  data() {
    return {
      imagePath: 'pipeline.png'  // Path to the pipeline image
    }
  }
}
</script>

<template>
  <div>
    <el-divider />

    <el-row justify="center">
      <h1 class="section-title">Overview of the AuraLuxMuse Pipeline</h1>
    </el-row>

    <!-- Insert image and caption -->
    <el-row justify="center">
      <el-col :xs="24" :sm="20" :md="16" :lg="12" :xl="12">
        <figure>
          <img :src="imagePath" class="chart-image" alt="AuraLuxMuse Pipeline" />
          <figcaption class="image-caption">
            Music and lighting data are individually preprocessed before entering LAMP for contrastive learning. Preference representations are injected via the PAMoE to enhance cue sequence encoding. The learned music and cue representations jointly inform the cue retriever, which selects Top-K lighting cues from the cue sequence corpus. Retrieval is guided by Metadata from the Metadata Predictor.
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