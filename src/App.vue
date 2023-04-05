<template>
  <div class="menu">
    <a v-for="a in 메뉴들" :key="a">{{ a }}</a>
  </div>
  <img alt="Vue logo" src="./assets/logo.png" />

  <div v-for="(원룸, i) in proroducts" :key="원룸">
    <h4>{{ 원룸 }}</h4>
    <div>{{ price[i] }}만원</div>
    <button @click="increase(i)">허위매물신고</button
    ><span>신고수 : {{ 신고수[i] }}</span>
  </div>
</template>

<script>
export default {
  name: "App",
  data() {
    return {
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
