<template>
  <modalTop :원룸들 = "원룸들" :popupOpenCount="popupOpenCount" :모달창오픈여부="모달창오픈여부" @closePopup="모달창오픈여부 = false"></modalTop>
  <div>
    <div class="menu">
      <a v-for="keyname in menus" :key="keyname">{{ keyname }}</a>
    </div>
    <DisCountRoom></DisCountRoom>
    <Card :원룸 = "원룸들[i]" v-for="(room, i) in 원룸들" :key="room" @openModal="모달창오픈여부 = true; popupOpenCount = $event"></Card>
  </div>


</template>

<script>
import oneRoomData from './assets/oneRoom.js';
import DisCountRoom from './DiscountRoom.vue';
import ModalTop from './ModalTop.vue';
import Card from './Card.vue';

export default {
  name: 'App',
  data(){
    return{ 
      모달창오픈여부 : false,
      popupOpenCount : 0,
      신고수1 : 0,
      신고수2 : 0,
      신고수3 : 0,
      menus : ['home', 'Shop', 'About'],
      products : ['역삼', '천호', '마포구'],
      원룸들 : oneRoomData,
    }
  },
  components:{
    DisCountRoom : DisCountRoom,
    ModalTop,
    Card,
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
.discount {
  background: #eee;
  padding: 10px;
  margin:10px;
  border-radius:5px;
}
</style>
