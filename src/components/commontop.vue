<template>
  <div id="commontop">
    <div class="main">
      <div class="logo clearfloat">
        <img src="http://unesmall.b0.upaiyun.com/unes_pro/01.png"/>
      </div>

      <ul class="topnavul clearfloat">
        <li id="navhuiyuan" @click="goHuiyuan">会员</li>
        <li class="active">检测</li>
        <li>肌肤分析</li>
        <li>分析报告</li>
      </ul>
      <div class="title_rig">
        <div>
          <img src="http://unesmall.b0.upaiyun.com/unes_pro/icon_user.png">
          {{mendian}}
        </div>

        <div @click="logout" class="hoverLogout" style="display: none;">退出</div>
      </div>

      <div class="title_rig1 icon_back" @click="fanhuiup"><img src="http://ws2.unescn.com/unes/img/icon_back.png">返回
      </div>

    </div>

  </div>
</template>
<script>
  export default {
    name: 'App',
    data() {
      return {
        msg: 'helloworld',
        mendian: ''
      }
    },
    created: function () {
      var storage = window.localStorage;
      this.mendian = storage.getItem("mendian");
    },
    methods: {

      logout: function () {
        this.$router.push('/login')
      },
      goHuiyuan: function () {
        this.$router.push('/huiyuan')
      },
      fanhuiup: function () {
        this.$router.back(-1)
      }
    },
    mounted: function () {

      $(document).click(function () {
        $(".hoverLogout").fadeOut();
      });
      $(".title_rig").click(function (event) {
        event.stopPropagation();
        $(".hoverLogout").slideDown()
      })

      var documenwidth=document.body.clientWidth;
      if(documenwidth>1364) {
        $(".title_rig").hover(function (event) {
          $(".hoverLogout").addClass("divshow")
        }, function () {
          $(".hoverLogout").removeClass("divshow")
        })
      }

    },
    watch: {}
  }
</script>
<style scoped>

  #commontop .main .logo img {
    margin-top: 5px;
  }

  #navhuiyuan {
    cursor: pointer;
  }

  .icon_back {
    right: 0px !important;
  }

  /*.hoverLogout{*/
  /*text-align: center;*/
  /*font-size: 14px;*/
  /*position: absolute;*/
  /*height: 40px;*/
  /*width: 66px;*/
  /*bottom: -20px;*/
  /*left: 0px;*/
  /*background-color: #051419;*/
  /*color: white;*/
  /*cursor: pointer;*/
  /*display: none;*/
  /*top: 40px;*/
  /*}*/
  .title_rig {
    float: right;
    position: absolute;
    right: 69px;
    color: white;
    font-size: 14px;
    margin-left: 20px;
    top: 0;
    line-height: 41px;
  }
  .title_rig1 {
    float: right;
    position: absolute;
    right: 69px;
    color: white;
    font-size: 14px;
    margin-left: 20px;
    top: 0;
    line-height: 41px;
  }

  .title_rig img,.title_rig1 img {
    vertical-align: middle;
  }

  .topnavul li:nth-child(1) {
    margin-left: 40px;
  }

  .topnavul {
    margin-left: 20px;
  }

  .topnavul li {
    float: left;
    font-size: 15px;
    margin-right: 20px;
    color: #4f5455;
  }

  #commontop {
    width: 100%;
    height: 40px;
    line-height: 40px;
    background-color: #051419;
    position: fixed;
    top: 0;
    z-index: 3;
  }

  #commontop .main {
    width: 50%;
    min-width: 1100px;
    height: 40px;
    line-height: 40px;
    background-color: #051419;
    position: fixed;
    margin: auto;
    top: 0;
    left: 0;
    right: 0;
    z-index: 99;
  }

  #commontop .main .logo {
    float: left;
  }
</style>
