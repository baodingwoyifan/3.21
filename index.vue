<template>
  <div>
    <!-- <el-row :gutter="10">
      <el-col :xs="8" :sm="6" :md="4" :lg="3" :xl="1">
         <el-menu :xs="8" :sm="6" :md="4" :lg="3" :xl="1" class="right" mode="horizontal">
        <el-menu-item v-for="item in 8" :key="item" index="1"
          >处理中心</el-menu-item
        >
      </el-menu>
      </el-col>
    </el-row> -->
    <el-row :gutter="10">
      <el-col :xs="8" :sm="6" :md="4" :lg="3" :xl="1">
        <el-menu default-active="2">
          <el-menu-item v-for="item in 20" :key="item" index="1">
            <i class="el-icon-setting"></i>
            <span slot="title">导航{{ item }}</span>
          </el-menu-item>
        </el-menu></el-col
      >
      <el-col style="height: 80px" :xs="16" :sm="18" :md="20" :lg="21" :xl="23">
        <el-col :xs="22" :sm="22" :md="22" :lg="22" :xl="24">1</el-col>
        <el-col :xs="2" :sm="2" :md="2" :lg="2">
          <i v-if="kai" class="el-icon-search"></i>
          <i v-else class="el-icon-house"></i>
        </el-col>
      </el-col>
       <el-button @click="getlists" type="info">重新获取</el-button>
    </el-row>
  </div>
</template>

<script>
import axios from "axios"
export default {
  data() {
    return {
      num: 1,
      kai:false
    };
  },
  methods: {
  async  getlists() {
      let datas =await axios('http://jsonplaceholder.typicode.com/posts')
      console.log(datas);

    },
  },
};
</script>
<style lang="less" scoped>
.el-col {
  border-radius: 4px;
}
.bg-purple-dark {
  background: #99a9bf;
}
.bg-purple {
  background: #d3dce6;
}
.bg-purple-light {
  background: #e5e9f2;
}
.grid-content {
  border-radius: 4px;
  min-height: 36px;
}
.right {
  position: absolute;
  top: 0;
  left: 200px;
  z-index: 10;
}
.z {
  position: absolute;
  top: 0;
  right: 0;
}
</style>
