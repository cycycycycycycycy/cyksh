<template>
  <div class="container">
      <div class="login">
    <!-- <img :src="imgSrc" width="100%" height="100%" alt="" /> -->
  <div class="loginPart">
    <h2>系统登录</h2>
  <el-form
      :model="ruleForm2"
      :rules="rules2"
      status-icon
      ref="ruleForm2"
      label-position="left"
      label-width="0px"
      class="demo-ruleForm login-page">
      <el-form-item prop="username" class="inputElement">
        <el-input
          type="text"
          v-model="ruleForm2.username"
          auto-complete="off"
          placeholder="用户名"
        ></el-input>
      </el-form-item>
      <el-form-item prop="password" class="inputElement">
        <el-input
          type="password"
          v-model="ruleForm2.password"
          auto-complete="off"
          placeholder="密码"
        ></el-input>
      </el-form-item>
      <!-- <el-checkbox v-model="checked" class="rememberme">记住密码</el-checkbox> -->
      <el-form-item style="width: 100%">
        <el-button
          type="primary"
          style="width: 100%"
          @click="handleSubmit"
          :loading="logining"
          >登录</el-button
        >
      </el-form-item>

  </el-form>
  </div>
  </div>
    <!-- 分组5d5409d0-88cb-11ec-9c17-a55b5fb2181b开始-->
    <div id="item5d5409d0-88cb-11ec-9c17-a55b5fb2181b">
      <!-- 组件1b0c5a00-87fe-11ec-8e64-7d8914ef0c2d开始-->

      <div id="item1b0c5a00-87fe-11ec-8e64-7d8914ef0c2d"></div>
      <!-- 组件1b0c5a00-87fe-11ec-8e64-7d8914ef0c2d结束-->

      <!-- 组件560b9120-88cb-11ec-9c17-a55b5fb2181b开始-->

      <div id="item560b9120-88cb-11ec-9c17-a55b5fb2181b">
        <img
          src="@/assets/images/9e271b27-1672-4db3-be06-c1da48808801.png"
          alt=""
          :style="{ width: '100%', height: '100%' }"
        />
      </div>
      <!-- 组件560b9120-88cb-11ec-9c17-a55b5fb2181b结束-->

      <!-- 组件93371f45-e76d-4bb0-ba19-e78b064fd377开始-->

      <div id="item93371f45-e76d-4bb0-ba19-e78b064fd377">
        <img
          src="@/assets/images/55872135-6c56-4778-9420-8ac3228b0ab8.png"
          alt=""
          :style="{ width: '100%', height: '100%' }"
        />
      </div>
      <!-- 组件93371f45-e76d-4bb0-ba19-e78b064fd377结束-->

      <!-- 组件df8c5c30-88c7-11ec-a2b5-4de1a34eab66开始-->

      <div
        id="itemdf8c5c30-88c7-11ec-a2b5-4de1a34eab66"
        :style="{
          fontSize: '18px',
          color: 'rgba(255, 255, 255,1)',
          textShadow: '6 5 5 rgba(15, 146, 255, 1)',
          lineHeight: '60px',
          textAlign: 'right',
          fontWeight: 'bold',
          letterSpacing: '2px',
        }"
      ></div>
      <!-- 组件df8c5c30-88c7-11ec-a2b5-4de1a34eab66结束-->
    </div>
    <!-- 分组5d5409d0-88cb-11ec-9c17-a55b5fb2181b结束-->

    <!-- 分组77238d40-88cb-11ec-9c17-a55b5fb2181b开始-->
    <div  id="item77238d40-88cb-11ec-9c17-a55b5fb2181b">
      <!-- 组件96c3fe9f-6ccc-46f1-959a-07443dd198c1开始-->

      <div id="item96c3fe9f-6ccc-46f1-959a-07443dd198c1">
        <img
          
          src="@/assets/images/31aa176c-a85b-4452-a2d8-8465cf6cd405.png"
          alt=""
          :style="{ width: '100%', height: '100%' }"
        />
      </div>
      <!-- 组件96c3fe9f-6ccc-46f1-959a-07443dd198c1结束-->

      <!-- 组件8361838c-a57c-4296-8219-0772c7e370a6开始-->

      <div id="item8361838c-a57c-4296-8219-0772c7e370a6">
        <img
          src="@/assets/images/76d19bbd-fee5-41ab-b20a-0dcec27c08e1.png"
          alt=""
          :style="{ width: '100%', height: '100%' }"
        />
      </div>
      <!-- 组件8361838c-a57c-4296-8219-0772c7e370a6结束-->
    </div>
    <!-- 分组77238d40-88cb-11ec-9c17-a55b5fb2181b结束-->
  </div>
</template>

<script>
import "@/assets/css/index.css"
import "@/assets/css/reset.css"
import "@/assets/css/custom-animation.css"
import * as echarts from "echarts"
import "echarts-wordcloud"
import "echarts-liquidfill"
import axios from "axios"
import QRCode from "qrcodejs2"
import { swiper, swiperSlide } from "vue-awesome-swiper"
import vueSeamlessScroll from "vue-seamless-scroll"
import "swiper/css/swiper.css"
import dayjs from "dayjs"
import "dayjs/locale/zh-cn"
import countTo from "vue-count-to"
import utils from "@/assets/js/utils.js"
import ThreeMap from "@/assets/js/ThreeMap.v2.js"
import AMapLoader from "@amap/amap-jsapi-loader"
import ThreeEarth from "@/assets/js/EarthMap/ThreeEarth.js"

import loading from "@/assets/components/loading/index.vue"
export default {
data() {
      return {
        // imgSrc: 'https://gimg2.baidu.com/image_search/src=http%3A%2F%2Ffile05.16sucai.com%2F2015%2F0615%2F0f9320e353671b9b02049dec80a7fde3.jpg&refer=http%3A%2F%2Ffile05.16sucai.com&app=2002&size=f9999,10000&q=a80&n=0&g=0n&fmt=jpeg?sec=1649492098&t=7809417f3b2a05a3486ae112253acbad',
        
        logining: false,
      ruleForm2: {
        username: "admin",
        password: "123456",
      },
      rules2: {
        username: [
          {
            required: true,
            message: "请输入用户名",
            trigger: "blur",
          },
        ],
        password: [
          { required: true, message: "请输入密码", trigger: "blur" },
        ],
      },
      checked: false,
      }
    },
  components: {
    swiper,
    swiperSlide,
    vueSeamlessScroll,
    countTo,
    "wt-loading": loading,
  },
  mounted() {
    this.$nextTick(() => {
      document.getElementsByClassName("container")[0].style.transform = `
        scaleX(${window.innerWidth / 1920}) 
        scaleY(${window.innerHeight / 1080})`

    /**
     *
     * 窗口发生改变自动刷新页面
     * 这样做不太友好，一般做法当前页面大小发生改变去重新加载echarts对象
     * 最好自行修改一下，当然。不要也可以，不会影响功能使用
     *
     */
    window.onresize = () => location.reload()
      playAnimation("#item5d5409d0-88cb-11ec-9c17-a55b5fb2181b", [
        {
          type: "fadeInDown",
          name: "向下移入",
          delayed: 0,
          loop: false,
          frequency: 1,
          duration: 1,
          isPlayer: false,
          isDisabled: false,
        },
      ])

      /**
       *
       * @param {*} id
       * @param {*} animations
       * 执行动画库函数【不用修改,可自行调整位置】
       * 声明初始值
       * 判断动画是否结束
       */
      function playAnimation(id, animations) {
        let index = 0
        let ele = document.querySelector(id)
        setAnimation(ele, animations[index])
        ele.addEventListener("webkitAnimationEnd", function () {
          if (index < animations.length - 1) {
            index++
            setAnimation(ele, animations[index])
          }
        })
      }

      /**
       *
       * @param {*} element
       * @param {*} animation
       * 执行动画库函数【不用修改,可自行调整位置】
       * 取index对应的动画
       * 给元素animation重新赋值
       */
      function setAnimation(element, animation) {
        const action = `${animation.duration * 1000}ms ease ${
          animation.delayed * 1000
        }ms ${
          animation.loop ? "infinite" : animation.frequency
        } normal both running ${animation.type}`
        element.style.animation = action
      }
    })

    // 自适应宽度处理

    this.method1b0c5a00_87fe_11ec_8e64_7d8914ef0c2d()

    this.method560b9120_88cb_11ec_9c17_a55b5fb2181b()

    this.method93371f45_e76d_4bb0_ba19_e78b064fd377()

    this.methoddf8c5c30_88c7_11ec_a2b5_4de1a34eab66()

    this.method96c3fe9f_6ccc_46f1_959a_07443dd198c1()

    this.method8361838c_a57c_4296_8219_0772c7e370a6()
  },
  methods: {
        handleSubmit(event) {
      this.$refs.ruleForm2.validate((valid) => {
        if (valid) {
          this.logining = true;
          if (
            this.ruleForm2.username === "admin" &&
            this.ruleForm2.password === "123456"
          ) {
            this.logining = false;
            const token = Date.parse(new Date());
            const res = [
              {
                name: "books",
                path: "/books",
                label: "书",
                icon: "-eleme",
                url: "books",
              },
              {
                name: "goods",
                path: "/goods",
                label: "商品",
                icon: "-eleme",
                url: "goods",
              },
              {
                label: "其他",
                icon: "-eleme",
                children:[
                  {
                name: "other1",
                path: "/other1",
                label: "其他1",
                icon: "-eleme",
                url: "others/other1",
              },
              {
                name: "other2",
                path: "/other2",
                label: "其他2",
                icon: "-eleme",
                url: "others/other2",
              },
              ]
              
              },
            ];
            this.$store.commit("clearMenu");
            this.$store.commit("setMenu", res);
            this.$store.commit("setToken", token);
            this.$store.commit("addMenu", this.$router);
            // sessionStorage.setItem("user", this.ruleForm2.username);
            this.$router.push({ path: "/home" });
          } else {
            this.logining = false;
            this.$alert("用户名或密码错误!", {
              confirmButtonText: "ok",
            });
          }
        } else {
          console.log("error submit!");
          return false;
        }
      });
    },
    method1b0c5a00_87fe_11ec_8e64_7d8914ef0c2d() {
      // 基于准备好的dom，初始化echarts实例
      // 指定图表的配置项
      let option = {
        color: [],
        textColor: "rgba(255, 255, 255, 1)",
        fontSize: 32,
        key: "H1",
        fontStyle: "normal",
        textAlign: "center",
        lineHeight: 1,
        justifyContent: "center",
        alignItems: "center",
        textShadow: {
          show: false,
          x: 0,
          y: 0,
          value: 14,
          color: "rgba(15, 146, 255,1)",
        },
      }

      // 指定文字的数据
      let data = [{ data: "可视化运维平台" }]

      //映射
      data = data.map((item) => {
        return { data: item["data"] }
      })
      let parentNode = document.getElementById(
        "item1b0c5a00-87fe-11ec-8e64-7d8914ef0c2d"
      )
      parentNode.style.color = option.textColor
      parentNode.style.display = "flex"
      parentNode.style.justifyContent = option.justifyContent
      parentNode.style.alignItems = "center"
      parentNode.style.textAlign = option.textAlign
      let textShadow = option.textShadow.show
        ? {
            textShadow: `${option.textShadow.x}px ${option.textShadow.y}px ${option.textShadow.value}px ${option.textShadow.color}`,
          }
        : {}
      parentNode.style.textShadow = textShadow.textShadow
      parentNode.style.fontStyle = option.fontStyle
      parentNode.innerHTML = null
      let titleNode = document.createElement(option.key)
      titleNode.innerText = data[0].data
      parentNode.appendChild(titleNode)
    },

    method560b9120_88cb_11ec_9c17_a55b5fb2181b() {},

    method93371f45_e76d_4bb0_ba19_e78b064fd377() {},

    methoddf8c5c30_88c7_11ec_a2b5_4de1a34eab66() {
      // 获取当前时间的配置项
      let option = {
        format: "YYYY/MM/DD HH:mm:ss",
        textStyle: {
          fontSize: 18,
          color: "rgba(255, 255, 255,1)",
          textShadow: {
            show: false,
            x: 6,
            y: 5,
            value: 5,
            color: "rgba(15, 146, 255, 1)",
          },
          lineHeight: 60,
          textAlign: "right",
          fontWeight: "bold",
          letterSpacing: 2,
        },
      }
      // 时间节点
      let timeDom = document.querySelector(
        "#itemdf8c5c30-88c7-11ec-a2b5-4de1a34eab66"
      )
      // 使用dayjs获取当前时间并按照配置要求进行格式化
      let value = dayjs().locale("zh-cn").format(option.format)
      timeDom.innerHTML = value
      // 时间按照秒级进行实时变动
      let timer = null
      if (timer !== null) clearInterval(timer)
      timer = setInterval(() => {
        value = dayjs().locale("zh-cn").format(option.format)
        timeDom.innerHTML = value
      }, 1000)
    },

    method96c3fe9f_6ccc_46f1_959a_07443dd198c1() {},

    method8361838c_a57c_4296_8219_0772c7e370a6() {},
  },
}
</script>

<style>
.loginPart{
    z-index: 999;
    position:absolute;
    /*定位方式绝对定位absolute*/
    top:50%;
    left:80%;
    /*顶和高同时设置50%实现的是同时水平垂直居中效果*/
    transform:translate(-50%,-50%);
    /*实现块元素百分比下居中*/
    width:450px;
    padding:30px;
    background: rgba(0,0,0,.5);
    /* background: #061422; */
    /*背景颜色为黑色，透明度为0.8*/
    box-sizing:border-box;
    /*box-sizing设置盒子模型的解析模式为怪异盒模型，
    将border和padding划归到width范围内*/
    box-shadow: 0px 15px 25px rgba(0,0,0,.5);
    /*边框阴影  水平阴影0 垂直阴影15px 模糊25px 颜色黑色透明度0.5*/
    border-radius:15px;
    /*边框圆角，四个角均为15px*/
  }
  .loginPart h2{
    margin:0 0 30px;
    padding:0;
    color: #fff;
    text-align:center;
    /*文字居中*/
  }
  .loginPart .inputbox{
    position:relative;
  }
  .loginPart .inputElement input{
    width: 100%;
    padding:10px 0;
    font-size:16px;
    color:#fff;
    letter-spacing: 1px;
    /*字符间的间距1px*/
    margin-bottom: 30px;
    border:none;
    border-bottom: 1px solid #fff;
    outline:none;
    /*outline用于绘制元素周围的线
    outline：none在这里用途是将输入框的边框的线条使其消失*/
    background: transparent;
    /*背景颜色为透明*/
  }

  .login{
    width:100%;
    height:100%;
  }
  
  </style>
