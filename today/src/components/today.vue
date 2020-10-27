<template>
  <div style="{overflow: scroll}">
    <div class='naviBar' :style="{height: naviBarHeight+'px'}" v-if='show_barline'>
      <div class='statusBar' :style="{height: statusBarHeight+'px'}"></div>
      <div class='today' :style="{top: statusBarHeight+'px', height: naviBarHeight - statusBarHeight+'px'}">今日</div>
      <div class='line'></div>
    </div>
    <div>测试语句</div>
    <div>测试语句</div>
    <div>测试语句</div>
    <div>测试语句</div>
    <div>测试语句</div>
    <div>测试语句</div>
    <div>测试语句</div>
    <div>测试语句</div>
    <div>测试语句</div>
    <div>测试语句</div>
    <div>测试语句</div>
    <div>测试语句</div>
    <div>测试语句</div>
    <div>测试语句</div>
    <div>测试语句</div>
    <div>测试语句</div>
    <div>测试语句</div>
    <div>测试语句</div>
    <div>测试语句</div>
    <div>测试语句</div>
    <div>测试语句</div>
    <div>测试语句</div>
    <div>测试语句</div>
    <div>测试语句</div>
    <div>测试语句</div>
    <div>测试语句</div>
    <div>测试语句</div>
    <div>测试语句</div>
    <div>测试语句</div>
    <div>测试语句</div>
    <div>测试语句</div>
    <div>测试语句</div>
    <div>测试语句</div>
    <div>测试语句</div>
    <div>测试语句</div>
    <div>测试语句</div>
    <div>测试语句</div>
    <div>测试语句</div>
    <div>测试语句</div>
    <div>测试语句</div>
    <div>测试语句</div>
    <div>测试语句</div>
    <div>测试语句</div>
    <div>测试语句</div>
    <div>测试语句</div>
  </div>
</template>

<script>
export default {
  name: "today",
  data(){
    return {
      naviBarHeight: 70,
      statusBarHeight: 5,
      screenWidth: 1,
      naviBarOpacity: 1,
      show_barline: true,
    }
  },
  methods:{
    handleScroll(){
      var scrollTop = window.pageYOffset || document.documentElement.scrollTop ||
                      document.body.scrollTop;
      var distance = scrollTop;
      if(distance < this.screenWidth / 750 * 130){
        this.show_barline = false;
        this.naviBarOpacity = 0;
      }else if(distance < this.screenWidth / 750 * 210){
        this.show_barline = true;
        this.naviBarOpacity = 1;
      }else{
        this.show_barline = true;
        this.naviBarOpacity = (distance - this.screenWidth / 750 * 130)/(this.screenWidth / 750 * 80);
      }
    }
  },
  mounted: function () {
    window.addEventListener('scroll', this.handleScroll, true);  // 监听（绑定）滚轮滚动事件
  },
  destroyed: function () {
    window.removeEventListener('scroll', this.handleScroll);   //  离开页面清除（移除）滚轮滚动事件
  }
}
</script>

<style scoped>
  .naviBar{
    width: 100vw;
    position: fixed;
    top: 0;
    left: 0;
    background-color: rgba(255,255,255,0.8);
    -webkit-backdrop-filter: saturate(180%) blur(5px);
    backdrop-filter: saturate(180%) blur(10px);
  }
  .statusBar{
    width: 100%;
    opacity: naviBarOpacity;
  }
  .today{
    width: 100vw;
    display: flex;
    justify-content: center;
    align-items: center;
    font-size: 32px;
    font-weight: bold;
  }
  .line{
    width: 100%;
    height: 1px;
    background-color: #c6c6c8;
    position: absolute;
    bottom: 0;
  }
</style>
