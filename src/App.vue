<template>
  <div class="black-bg" v-if="modal == true" @click="modal = false">
    <div class="white-bg" @click.stop>
      <h4>상세페이지</h4>
      <p>상세페이지 내용</p>
      <button @click="modal = false">닫기</button>
    </div>
  </div>
  <div class="menu">
    <a v-for="a in menus" :key="a">{{ a }}</a>
  </div>
  <!-- HTML 태그안의 속성 데이터바인딩은 :src
  HTML 태그안의 내용 데이터바인딩은 {{ 어쩌구 }} -->
  <div v-for="d in data" :key="d.id">
    <img :src="d.image" class="room-img" />
    <h4 @click="modal = true">{{ d.title }}</h4>
    <p>{{ d.price }}</p>
  </div>
  <!-- <div>
    <img src="./assets/mentalout.jpeg" class="room-img" />
    <h4>{{ products[1] }}</h4>
    <p>{{ prices[1] }} 만원</p>
  </div>
  <div>
    <img src="./assets/neitio.jpeg" class="room-img" />
    <h4>{{ products[2] }}</h4>
    <p>{{ prices[2] }} 만원</p>
  </div> -->
</template>

<script>
import data from './data/post';

export default {
  name: 'App',
  data() {
    return {
      data: data,
      modal: false,
      report: [0, 0, 0],
      prices: [50, 60, 70],
      menus: ['Home', 'Products', 'About'],
      products: ['역삼동원룸', '천호동원룸', '마포구원룸'],
    };
  },
  methods: {
    increase() {
      this.report += 1;
    },
  },
  components: {},
};
</script>

<style>
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
}
body {
  margin: 0;
}
div {
  box-sizing: border-box;
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
</style>
