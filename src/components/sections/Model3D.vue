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

    <!-- Insert image and paragraph -->
    <el-row justify="center">
      <el-col :xs="24" :sm="20" :md="16" :lg="12" :xl="12">
        <img :src="imagePath" class="chart-image" alt="AuraLuxMuse Pipeline" />
        <p class="image-description">
          Music and lighting data are individually preprocessed before entering LAMP for contrastive learning. Preference representations are injected via the PAMoE to enhance cue sequence encoding. The learned music and cue representations jointly inform the cue retriever, which selects Top-K lighting cues from the cue sequence corpus. Retrieval is guided by Metadata from the Metadata Predictor. The Lighting Encoder adopts a transformer-based architecture with four self-attention heads and the Music Encoder is composed of a VGGish network with multilayer perceptrons, all selected based on ablation studies. The Metadata Predictor is made up of several compression and regression modules made up of MLPs.
        </p>
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

.image-description {
  text-indent: 32px;
  font-family: "Helvetica Neue", Arial, -apple-system, BlinkMacSystemFont, "Segoe UI", Roboto, Oxygen, Ubuntu, Cantarell, "Open Sans", sans-serif;
  font-size: 16px;
  color: #000;
  line-height: 1.6; /* Adjusted from 1 to 1.6 for better readability */
  text-align: justify;
}
</style>