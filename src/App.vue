<template>
  <div class="black-bg" v-if="모달창오픈 == true">
    <div class="white-bg">
      <h4>상세 페이지</h4>
      <p>상세 페이지 내용</p>
      <button @click="모달창오픈 = false">닫기</button>
    </div>
  </div>



  <div class="menu">
    <a v-for="a in menu" :key="a">{{a}}</a>
  </div>

  <div v-for="(a,i) in 3" :key="i">
    <img :src="oneroom[i].image" alt="">
    <h4>{{oneroom[i].title}}</h4>
    <p>{{oneroom[i].price}}원</p>
    <button @click="increase(i)">허위 매물 신고</button>
    <span>신고수 : {{신고[i]}}</span>
  </div> 
</template>

<script>
import data from './assets/post.js';


export default {
  name: 'App',
  data(){
    return {
      oneroom : data,
      모달창오픈 : true,
      신고 : [0, 0, 0],
      menu : ['Home', 'Shop', 'About'],

    }
  },
  methods: {
    increase(i){
      this.신고[i]++;
    }
  },

  components: {
    
  }
}
</script>

<style>
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
}

.menu {
  background: darkslateblue;
  padding: 15px;
  border-radius: 5px;
}

.menu a {
  color: white;
  padding: 10px;
}

.room-img {
  width: 100%;
  margin-top: 40px;
}

body {
  margin: 0;
}

div {
  box-sizing: border-box;
}

.black-bg {
  width: 100%; height: 100%;
  background: rgba(0,0,0,0,5);
  position: fixed; padding: 20px;
}

.white-bg {
  width: 100%; background: white;
  border-radius: 8px;
  padding: 20px;
}
</style>
