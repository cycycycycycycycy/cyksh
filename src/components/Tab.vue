<template>
  <div class="bgc">
    <el-menu
      :default-active="activeIndex"
      text-color="#fff"
      active-text-color="#fff"
      class="el-menu-demo"
      mode="horizontal"

    >
      <el-menu-item
        v-for="item in noChildren"
        :index="item.path"
        :key="item.path"
        @click="clickMenu(item)"
        class="img"
        style="margin-left: 5px;"
      >
        <div class="_img">{{ item.label }}</div>
      </el-menu-item>
      <el-submenu
        v-for="item in hasChildren"
        :index="item.path + ''"
        :key="item.path"
        class="img"
        style="height: 35px; line-height: 35px"
      >
        <template slot="title">
          <div class="_img">{{ item.label }}</div>
        </template>
        <el-menu-item
          v-for="subItem in item.children"
          :key="subItem.path"
          :index="subItem.path"
          @click="clickMenu(subItem)"
          >{{ subItem.label }}</el-menu-item
        >
      </el-submenu>
    </el-menu>
  </div>
</template>

<script>
export default {
  data() {
    return {
      activeIndex: "1",
      activeIndex2: "1",
      menu: [],
    };
  },
  mounted() {
    document.getElementsByClassName("bgc")[0].style.transform = `
        scaleX(${window.innerWidth / 1920}) 
        scaleY(${window.innerHeight / 1080})`;

    /**
     *
     * 窗口发生改变自动刷新页面
     * 这样做不太友好，一般做法当前页面大小发生改变去重新加载echarts对象
     * 最好自行修改一下，当然。不要也可以，不会影响功能使用
     *
     */
    window.onresize = () => location.reload();
  },
  methods: {
    handleOpen(key, keyPath) {
      console.log(key, keyPath);
    },
    handleClose(key, keyPath) {
      console.log(key, keyPath);
    },
    clickMenu(item) {
      this.$router.push({
        name: item.name,
      });
      this.$store.commit("selectMenu", item);
    },
  },
  computed: {
    noChildren() {
      return this.asyncMenu.filter((item) => !item.children);
    },
    hasChildren() {
      return this.asyncMenu.filter((item) => item.children);
    },
    isCollapse() {
      return this.$store.state.tab.isCollapse;
    },
    asyncMenu() {
      return this.$store.state.tab.menu;
    },
  },
};
</script>

<style >
.bgc {
  position: absolute;
  left: 50%;
  top: 3%;
  z-index: 999;
}
.el-menu {
  height: 35px;
  line-height: 35px !important;
  padding: 0;
  background-color: rgba(255, 255, 255, 0);
}
.el-submenu {
  margin-left: 5px;
  height: 35px !important;
  padding: 0;
  /* background-color: rgba(255, 255, 255, 0.3) !important; */
  background-color: rgba(33, 180, 239, 0.3) !important;
  

  font-size: 100%;

  line-height: 35px !important;
}
.el-submenu .el-menu-item {
  /* padding: 0; */
  margin-left: 5px;
  height: 35px !important;
  background-color: rgba(33, 180, 239, 0.3) !important;
  font-size: 100%;
  line-height: 35px !important;
}
.el-submenu.is-active {
  background-color: rgba(128, 35, 41, 0.7) !important;
  color: #fff;
  height: 35px !important;
  line-height: 35px !important;
}
.img {
  /* background-image: linear-gradient(to top, #21b4ef 0%, #fff 100%); */
  background-color: rgba(35, 152, 214, 0.5) !important;

  /* width: 100px; */
  /* height: 30px; */
  text-align: left !important;
  transform: skewX(-45deg);
}
._img {
  transform: skewX(45deg);
}
.el-menu-item {
  /* padding: 0; */
  margin-left: 5px;
  height: 35px !important;
  background-color: rgba(33, 180, 239, 0.3) !important;
  font-size: 100%;
  line-height: 35px !important;
}
.el-submenu__title {
  /* padding: 0; */
  background-color: rgba(33, 180, 239, 0) !important;
  
  height: 35px;
  font-size: 100% !important;
  line-height: 35px !important;
}
.el-menu--horizontal > .el-submenu .el-submenu__title {
  height: 35px;
  font-size: 100%;
}
.el-menu-item.is-active {
  background-color: rgba(128, 35, 41, 0.7) !important;

  color: #fff;
}
.el-menu-item.is-active span {
  color: #fff !important;
}
.el-menu.el-menu--horizontal {
  border-bottom: solid 0px #e6e6e6;
}
.el-icon-arrow-down:before {
  content: "";
}
</style>