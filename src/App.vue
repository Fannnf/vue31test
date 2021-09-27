<template>
  <div>
     <h2>请输入您的学考成绩</h2>
 
     <h4>语文:</h4>
    <input type="text" v-model="sub.chi">
     <h4>数学：</h4>
    <input type="text" v-model="sub.mat">
     <h4>外语：</h4>
    <input type="text" v-model="sub.eng">
     <h4>物理：</h4>
    <input type="text" v-model="sub.phy">
     <h4>化学：</h4>
    <input type="text" v-model="sub.che">
     <h4>生物：</h4>
    <input type="text" v-model="sub.bio">
     <h4>政治：</h4>
    <input type="text" v-model="sub.pol">
     <h4>历史：</h4>
    <input type="text" v-model="sub.his">
     <h4>地理：</h4>
    <input type="text" v-model="sub.geo">
     <h4>技术：</h4>
    <input type="text" v-model="sub.tec">
    <br>
    <br>
    <button @click="submit">确认提交</button>
  </div>
</template>

<script>
import {reactive} from 'vue'

export default {
  name: 'App',
  setup(){
    let sub = reactive({
      chi : 'A',//语文
      mat : 'A',//数学
      eng : 'A',//外语
      phy : 'A',//物理
      che : 'A',//化学
      bio : 'A',//生物
      pol : 'A',//政治
      his : 'A',//历史
      geo : 'A',//地理
      tec : 'A',//技术
    })
    let all = reactive([])
    // let num = reactive({
    //   a:10,
    //   b:0,
    //   c:0,
    //   d:0
    // })

    // watch(sub,()=>{

    // })

    // function dis() {
    //   if (sub.chi=='A') {
        
    //   }
    // }

    function submit(){
      let flag=confirm('请确认您的学考成绩信息\n语文：'+sub.chi+'     数学：'+sub.mat+'     外语：'+sub.eng+'\n物理：'+sub.phy+'     化学：'+sub.che+'     生物：'+sub.bio+'\n政治：'+sub.pol+'     历史：'+sub.his+'     地理：'+sub.geo+'\n技术：'+sub.tec);
      if (flag) {
        all=[trans(sub.chi),trans(sub.mat),trans(sub.eng),trans(sub.phy),trans(sub.che),trans(sub.bio),trans(sub.pol),trans(sub.his),trans(sub.geo),trans(sub.tec)]
        console.log(all);
        alert('提交成功！');
      }
    }

    function trans(level) {//把等级转换为数字，A为1
      if (level=='A') {
        return 1;
      } 
      else if (level=='B') {
        return 2;
      }
      else if (level=='C') {
        return 3;
      }
      else if (level=='D') {
        return 4;
      }
      else {
        alert('您输入的内容有误，请重新输入！');
      }    
      }

    return{
      sub,
      submit,
      all,
      trans
    }
  }
}
</script>

