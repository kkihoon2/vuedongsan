<template>


  <div class="black-bg" v-if="modalOpened === true">
<!--    (v-else , v-else-if도 존재함)-->
    <div class="white-bg">
      <h4>{{ onerooms[modalNum].title }}</h4>
      <p>상세페이지내용</p>
      <p>{{ onerooms[modalNum].price }}</p>
      <button @click="modalOpened=false">닫어</button>
    </div>
  </div>



  <input v-model="message">
  <p>{{ message }}</p>


  <button @click="modalOpened=true">열어</button>
<!--  <div>-->
<!--    <p v-for="hey in menus" :key="hey">{{ hey }}</p>-->
<!--  </div>-->

  <div v-for="(data,i) in onerooms" :key="i">
    <h1 @click = "modalOpened = true; modalNum=i">{{ data.id }}</h1>
<!--    todo: modalNum에 data를 넣었을때는 왜 작동을 하지 않을까?-->
    <h2>title : {{ data.title }}</h2>
    <h3>content : {{ data.content }}</h3>
    <img :src="data.image">
<!--    속성데이터바인딩-->
    <p>{{ data.price }}</p>
<!--    내용데이터바인딩-->
  </div>


</template>

<script>


import datas from './data/post';



export default {
  name: 'App',
  components: {},
  data() {
    return {
      onerooms: datas,
      modalOpened: false,
      calls: [0, 0, 0],
      menus: ['home', 'shop', '마포구원룸'],
      message: "hello",
      users: {},
      modalNum : 0
    }
  },
  methods: {
    increase() {

    },

  },
  watch: {
    message: function (value) {
      console.log(value);
    }
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
  margin-top: 60px;
}

.discount{
  background: #eee;
  padding: 10px;
  margin: 10px;
  border-radius: 5px;
}
body {
  margin: 0
}

div {
  box-sizing: border-box
}

.black-bg {
  width: 100%;
  height: 100%;
  background: rgba(0, 0, 0, 0.5);
  position: fixed;
  padding: 20px;
}

.white-bg {
  width: 100%;
  background: white;
  border-radius: 8px;
  padding: 20px;
}
</style>
