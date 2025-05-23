<script setup>
import abstract from '../mds/abstract.mdx';
</script>

<template>
  <div>
    <el-divider />

    <el-row justify="center">
      <el-col :xs="24" :sm="20" :md="16" :lg="12" :xl="12">
        <div class="abstract-container">
          <abstract />
        </div>
      </el-col>
    </el-row>
  </div>
</template>

<style scoped>
/* Style the abstract container */
.abstract-container {
  text-indent: 32px;
  font-family: "Helvetica Neue", Arial, -apple-system, BlinkMacSystemFont, "Segoe UI", Roboto, Oxygen, Ubuntu, Cantarell, "Open Sans", sans-serif;
  font-size: 16px;
  color: #000;
  line-height: 1.6; /* Adjusted from 1 to 1.6 for better readability */
  text-align: justify;
}

/* Ensure paragraphs within abstract have consistent spacing and first-line indent */
.abstract-container p {
  margin: 0 0 1em 0;
  text-indent: 1.5em; /* Add first-line indent */
}
</style>