<template>
  <div class="black-bg" v-if="modalState == true">
    <div class="white-bg">
      <h4>상세페이지</h4>
      <p>내용</p>
      <button @click="modalState = false">닫기</button>
    </div>
  </div>

  <div class="menu">
    <a v-for="a in menu" :key="a">{{ a }}</a>
  </div>

  <div>
    <img src="./assets/folder.png" />
    <h4 @click="modalState = true">{{ products[0] }}</h4>
    <p>50만원</p>
    <button @click="reportNum[0]++">🚨 허위매물신고</button>
    <span> 신고 수 : {{ reportNum[0] }}</span>
  </div>
  <div>
    <img src="./assets/folder.png" />
    <h4>{{ products[1] }}</h4>
    <p>70 만원</p>
    <button @click="reportNum[1]++">🚨 허위매물신고</button>
    <span> 신고 수 : {{ reportNum[1] }}</span>
  </div>
  <div>
    <img src="./assets/folder.png" />
    <h4>{{ products[2] }}</h4>
    <p>70 만원</p>
    <button @click="reportNum[2]++">🚨 허위매물신고</button>
    <span> 신고 수 : {{ reportNum[2] }}</span>
  </div>

  <!-- <div v-for="(a, i) in products" :key="i">
    <h4>{{ a }}</h4>
    <p>50만원</p>
  </div> -->
</template>

<script>
export default {
  name: "App",
  data() {
    return {
      modalState: true,
      reportNum: [0, 0, 0],
      menu: ["Home", "Shop", "About"],
      products: ["역삼동 원룸", "천호동 원룸", "마포구 원룸"],
    };
  },
  methods: {
    reportNumPlus() {
      this.reportNum++;
    },
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

.menu {
  background-color: darkslateblue;
  padding: 15px;
  border-radius: 5px;
}
.menu a {
  color: white;
  padding: 10px;
}
img {
  width: 200px;
  height: 200px;
}

button {
  background-color: coral;
  border: 0;
  outline: 0;
  opacity: 0.9;
}
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
}
</style>
