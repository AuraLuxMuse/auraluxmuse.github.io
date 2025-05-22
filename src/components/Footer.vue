<script lang="ts" setup>
// 页脚需要的链接
const links = {
     Nerfies: "",
     Vue: "",
     Vite: "",
     ElementPlus: "",
     template: "",
}
</script>

<template>
  
  <div class="bg">
    
    <el-watermark :content="['JunyaoHu', 'Academic Project', 'Page Template']" :gap="['60','0']" :z-index="0">
      <el-row justify="center">
        <p class="footer">
          This template is inspired by 
          <a :href="links.Nerfies">Nerfies</a>,<br/>
          
          powered by 
          <a :href="links.Vue">Vue</a>, 
          <a :href="links.Vite">Vite</a>, and
          <a :href="links.ElementPlus">Element Plus</a>.<br/>
          
          You can fork🛠️ / star✨/ PR📃 from <a :href="links.template">here</a>.
        </p>
      </el-row>
    </el-watermark>
  </div>
</template>

<style scoped>

/* 页脚背景 */
.bg {
  background-color: rgb(235, 235, 235);
}

/* 页脚文字 */
.footer {
  text-align: center;
  margin: 20px;
  z-index: 1;
}

</style>