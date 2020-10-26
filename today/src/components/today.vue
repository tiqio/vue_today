<template>
  <div class='a'>
    sss
    
  <button @click="ss">ss</button>
  </div>
</template>

<script>
export default {
  name: "today",
  methods:{
    
    ss(){
      console.log('ss');
    }
  },
  mounted(){
      console.log("测试");
  }
}
</script>

<style scoped>
  .a{
    color: gold;
  }
</style>
