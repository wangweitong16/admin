<template>
  <el-container class="out">
    <el-header class="header">Header</el-header>
    <el-container>
      <el-aside width="200px" class="aside">
        <el-menu :default-openeds="['1', '3']">

          <el-submenu :index="item.index" v-for="item in aside" :key="item.id">
            <template slot="title"><i class="el-icon-menu"></i>{{item.title}}</template>
            <el-menu-item :index="item.index+'-'+ite.index" v-for="ite in item.children" :key="ite.id">{{ite.title}}</el-menu-item>
            <!-- <el-menu-item index="1-2">选项2</el-menu-item> -->
          </el-submenu>



<!-- 
          <el-submenu index="1">
            <template slot="title"><i class="el-icon-menu"></i>首页</template>
            <el-menu-item index="1-1">选项1</el-menu-item>
            <el-menu-item index="1-2">选项2</el-menu-item>
          </el-submenu>
          <el-submenu index="2">
            <template slot="title"
              ><i class="el-icon-menu"></i>权限管理</template
            >
            <el-menu-item index="2-1">选项1</el-menu-item>
            <el-menu-item index="2-2">选项2</el-menu-item>
          </el-submenu> -->
        </el-menu>
      </el-aside>
      <el-main class="main">Main</el-main>
    </el-container>
  </el-container>
</template>

<script>
export default {
  props: {},
  data() {
    return {
      aside: [
        { id: 0, title: "首页", index: 1, children: [
            {id: 0, title: "数据统计", index: 1, children: ""},
          ] 
        },
        {
          id: 1,
          title: "权限管理",
          index: 2,
          children: [
            { id: 0, title: "会员列表", index: 1, children: "" },
            { id: 1, title: "会员删除", index: 2, children: "" },
            { id: 2, title: "权限分类", index: 3, children: "" },
          ],
        },
        { id: 2, title: "创作管理", index: 3, children: "" },
        { id: 3, title: "系统设置", index: 4, children: "" },
      ],
    };
  },
  methods: {},
  components: {},
};
</script>

<style scoped lang="scss">
.el-header {
  background-color: #b3c0d1;
  color: #333;
  text-align: center;
  line-height: 60px;
}
.el-container {
  height: 100%;
}
.el-aside {
  background-color: #d3dce6;
  color: #333;
  text-align: center;
  line-height: 200px;
}

.el-main {
  background-color: #e9eef3;
  color: #333;
  text-align: center;
  line-height: 160px;
}

body > .el-container {
  margin-bottom: 40px;
}

.el-container:nth-child(5) .el-aside,
.el-container:nth-child(6) .el-aside {
  line-height: 260px;
}

.el-container:nth-child(7) .el-aside {
  line-height: 320px;
}
</style>
