<template>
    <div class="black-bg" v-if="모달창오픈여부 == true">
    <div class="white-bg">
      <img :src="원룸들[popupOpenCount].image" class="room-img">
      <h4>{{ 원룸들[popupOpenCount].title }}</h4>
      <p>{{ 원룸들[popupOpenCount].price }}원</p>
      <pre>{{ 원룸들[popupOpenCount].content }}</pre>
      <div>

      </div>
      <button @click="모달창오픈여부 = false">닫기</button>
    </div>
  </div>
</template>

<script>
export default {

}
</script>

<style>

</style>