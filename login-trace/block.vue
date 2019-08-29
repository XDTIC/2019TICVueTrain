<style>
.block {
  height: 30px;
  width: 30px;
  display: inline-block;
  border-radius: 10px;
}

.blockGreen{
  background-color: green;
}

.blockGrey{
  background-color: grey;
}
</style>

<template>
  <span class="block" :class="isLogin ? 'blockGreen' : 'blockGrey'" :title="dateStr">
    &nbsp;
  </span>
</template>

<script type="text/javascript">
  export default {
    name:"BlockComponent",
    props:{
      dateStr: String,
      isLogin: Boolean,
    },
    data(){
      return{
        
      }
    },
    methods:{
      clickA(){
        this.a++;
      },
      clickB(){
        this.b++;
      }
    }
  }
</script>