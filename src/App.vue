<template>
  <div class="black-bg" v-if="모달창열렸니">
    <div class="white-bg" @click="모달창열렸니 = false">
      <h4>상세페이지임</h4>
      <p>상세페이지 내용임</p>
    </div>
  </div>

  <div class="menu">
    <a v-for="a in 메뉴들" :key="a">{{ a }}</a>
  </div>

  <div v-for="(원룸, i) in 원룸들" :key="원룸">
    <img @click="모달창열렸니 = true" :src="원룸들[i].image" class="room-img" />
    <h4>{{ 원룸들[i].title }}</h4>
    <div>{{ 원룸들[i].price }}만원</div>
    <div>{{ 원룸들[i].content }}</div>
  </div>
</template>

<script>
import data from "./assets/data";

export default {
  name: "App",
  data() {
    return {
      원룸들: data,
      모달창열렸니: false,
      신고수: [0, 0, 0],
      메뉴들: ["Home", "Shop", "About"],
      proroducts: ["역삼동원룸", "천호동원룸", "마포구원룸"],
      price: [50, 60, 70],
    };
  },
  methods: {
    increase(i) {
      this.신고수[i] += 1;
    },
    함수2() {},
  },
  components: {},
};
</script>

<style>
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

.room-img {
  width: 100%;
  margin-top: 40px;
}

#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
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
</style>
