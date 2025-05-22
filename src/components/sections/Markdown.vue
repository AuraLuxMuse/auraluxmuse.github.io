<script setup>
import page from '../mds/md.mdx';
</script>

<template>
  <div>
    <el-divider />

    <el-row justify="center">
        <el-col :xs="24" :sm="20" :md="16" :lg="12" :xl="12">
            <page />
        </el-col>
    </el-row>
  </div>
</template>

<style scoped>
/* 调整 Markdown 表格样式 */
table {
  width: 100%;
  border-collapse: collapse;
  margin: 20px 0;
}

th, td {
  border: 1px solid #ddd;
  padding: 8px;
  text-align: center; /* 居中对齐 */
}

th {
  background-color: #f2f2f2;
  font-weight: bold;
}

tr:nth-child(even) {
  background-color: #f9f9f9;
}

/* 模拟 LaTeX 表格的加粗和斜体 */
strong {
  font-weight: bold;
}

em {
  font-style: italic;
}
</style>