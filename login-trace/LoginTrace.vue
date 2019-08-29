<style>
.block{
  margin: 2px;
}
</style>

<template>
  <div>
    <div v-if="!loadFinish">
      数据载入中...
    </div>
    <div v-else>
      <p>最近连续登录{{loginHitCount}}/天</p>
      <div>
        <block :date-str="dateStrAdapt(30-i)" :is-login="dateHit(30-i)" v-for="i in 10" :key="i"/>
      </div>
      <div>
        <block :date-str="dateStrAdapt(20-i)" :is-login="dateHit(20-i)" v-for="i in 10" :key="i"/>
      </div>
      <div>
        <block :date-str="dateStrAdapt(10-i)" :is-login="dateHit(10-i)" v-for="i in 10" :key="i"/>
      </div>
    </div>
  </div>
</template>

<script type="text/javascript">
import block from './block.vue';
export default {
  name:"LoginTrace",
  mounted(){
    this.today = new Date('2019-07-12'); // 假设当天为2019-07-12
    this.ajax(); // 模拟异步拉取服务器数据
  },
  data(){
    return {
      loadFinish: false, // 是否从服务器拉取到数据
      trace: [], // 登录日志轨迹
      today: new Date() // 当日时间
    }
  },
  computed:{
    loginHitCount(){ // 计算连续登录天数
      let count = 0;
      while(this.dateHit(count)) count++;
      return count;
    }
  },
  methods:{
    ajax(){ // 模拟AJAX操作
      setTimeout(()=>{
        this.trace.splice(0, this.trace.length);
        const result = { // 假设服务器拉取到的数据格式为 'yyyy-mm-dd'
          'loginTrace': ['2019-06-29', '2019-06-15','2019-07-01', '2019-07-02', '2019-07-08', '2019-07-10', '2019-07-11', '2019-07-12']
        }
        for(let i of result['loginTrace']){
          this.trace.push(i);
        }
        this.loadFinish = true; // 从服务器得到数据，修改标志
      }, 2000/* 延迟两秒拉取到数据 */);
    },
    dateStrAdapt(daysAgo){ // 格式化数据串，获取前daysAgo天的数据串
      let currentTick = new Date(this.today.getTime() - daysAgo*24*3600*1000);
      let year        = currentTick.getFullYear();
      let month       = currentTick.getMonth()+1 < 10 ? `0${currentTick.getMonth()+1}` : currentTick.getMonth()+1;
      let day         = currentTick.getDate()    < 10 ? `0${currentTick.getDate()}`    : currentTick.getDate();
      return `${year}-${month}-${day}`;
    },
    dateHit(daysAgo){ // 判断几天前的某一天是否登陆过
      return this.trace.indexOf(this.dateStrAdapt(daysAgo)) >= 0;
    }
  },
  components:{
    block
  }
}
</script>