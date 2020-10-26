<template>
  <div>
    
  </div>
</template>

<script>
export default {
  name: "today",
  methods:{
    handleScroll(){
      var scrollTop = window.pageYOffset || document.documentElement.scrollTop ||
                      document.body.scrollTop;

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
  
</style>
