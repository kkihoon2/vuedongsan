<template>
  <div class="black-bg" v-if="modalOpened === true">
    <!--    (v-else , v-else-if도 존재함)-->
    <div class="white-bg">
      <h4>{{ onerooms[modalNum].title }}</h4>
      <p>상세페이지내용</p>
      <p>{{ onerooms[modalNum].price }}</p>
<!--      <button @click=" modalOpened = false ">닫어</button> -->
<!--      props는 무조건 readonly임 값수정하면 안됨-->
      <button @click = "$emit('modal')">닫어</button>
    </div>
  </div>
</template>

<script>
export default {
  name : 'ModalBanner',
  props : {
    onerooms : Array,
    modalOpened : Boolean,
    modalNum : Number,
  }
}
</script>

<style>


</style>