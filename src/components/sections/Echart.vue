<script>
export default {
  data() {
    return {
      imagePath: 'dataset_procedure.png'  // Path to the dataset procedure image
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

    <!-- Insert image and paragraph -->
    <el-row justify="center">
      <el-col :xs="24" :sm="20" :md="16" :lg="12" :xl="12">
        <img :src="imagePath" class="chart-image" alt="Musilux Dataset Construction Procedure" />
        <p class="image-description">
          Initially, music and lighting cues are collected, and the distribution across scenarios is shown in the collection procedure. Alignment is performed at both the internal level of cues and the cross-modal level to synchronize music and lighting data. The resulting aligned sequences are then aggregated into Cue Sequence Corpus, constituting our Musilux Dataset.
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