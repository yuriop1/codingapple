<template>
  <div class="black-bg" v-if="모달창오픈여부 == true">
    <div class="white-bg">
      <h4>상세페이지</h4>
      <p>상세페이지내용</p>
      <button @click="모달창오픈여부 = false">닫기</button>
    </div>
  </div>
  <div>
    <div class="menu">
      <a v-for="keyname in menus" :key="keyname">{{ keyname }}</a>
    </div>
    <div>
      <img :src="원룸들[0].image" class="roomSize">
      <h4 @click="모달창오픈여부 = true">{{원룸들[0].title}}</h4>
      <p>{{원룸들[0].price}}원</p>
      <button @click="increase1">허위매물신고</button>
      <span>신고수 : {{ 신고수1 }}</span>
    </div>
    <div>
      <img :src="원룸들[1].image" class="roomSize">
      <h4 @click="모달창오픈여부 = true">{{원룸들[0].title}}</h4>
      <p>{{원룸들[0].price}}원</p>
      <button @click="increase2">허위매물신고</button>
      <span>신고수 : {{ 신고수2 }}</span>
    </div>
    <div>
      <img :src="원룸들[2].image" class="roomSize">
      <h4>{{products[2]}}</h4>
      <p>50만원</p>
      <button @click="increase3">허위매물신고</button>
      <span>신고수? : {{ 신고수3 }}</span>
    </div>
  </div>
</template>

<script>
import oneRoomData from './assets/oneRoom'

export default {
  name: 'App',
  data(){
    return{ 
      모달창오픈여부 : false,
      신고수1 : 0,
      신고수2 : 0,
      신고수3 : 0,
      menus : ['home', 'Shop', 'About'],
      products : ['역삼', '천호', '마포'],
      원룸들 : oneRoomData,
    }
  },
  methods : {
    increase1(){
      this.신고수1 +=1;
    },
    increase2(){
      this.신고수2 +=1;
    },
    increase3(){
      this.신고수3 +=1;
    },
  },
  components: {
  }
}

</script>

<style>
body {
  margin : 0;
}
div {
  box-sizing: border-box;
}
.black-bg {
  width: 100%; height:100%;
  background: rgba(0,0,0,0.5);
  position: fixed; padding: 20px;
}
.white-bg {
  width: 100%; background: white;
  border-radius: 8px;
  padding: 20px;
} 
.roomSize {
  width: 80%;
  margin-top: 40px;
}
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
}
.menu {
  background-color: #448fda;
  padding : 15px;
  border-radius : 5px;
}
.menu a {
  color :aliceblue;
  padding : 10px;

}
</style>
