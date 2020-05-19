<template>
<div class="body">
  <div class="wrapper">
    <div class="main">
      <div class="main_title">
        <p class="corplife">#corplife</p>
        <p class='titile_h1'>тайный <br>санта</p>
        <button v-if='loginStatus == "Error"' @click='toLogin'>Войти</button>
        <router-link v-else class="link" to="/profile"><button>Мой профиль {{loginStatus}} </button></router-link>
      </div>
      <div class="all">
        <p class="text">уже принимает участие</p>
        <div class="component">
          <p class='count'>340</p>
          <p class='countText'>всего</p>
        </div>
        <div class="component">
          <p class='count'>3</p>
          <p class='countText'>дп</p>
        </div>
        <div class="component">
          <p class='count'>45</p>
          <p class='countText'>из отдела</p>
        </div>
      </div>
    </div>
  </div>
</div>
</template>

<script>
export default {
  name: "MainBlock",
  props: {
    loginStatus: {}
  },
  methods: {
    toLogin() {
      this.$emit('toLogin')
    }
  }
}
</script>

<style scoped>
a {
  color: #fff;
  text-decoration: none;
}

.body {
  padding: 10px;
  height: 600px;
  background-color: #00A460;
  background-image: url("../../assets/santas/santa_homepage.svg");
  background-size: cover;
  background-repeat: no-repeat;
  box-shadow: 0px 7px 20px rgba(0, 0, 0, 0.1);
  border-radius: 0px 0px 150px 150px;
}

.wrapper {
  margin-right: auto;
  margin-left: auto;
  max-width: 70%;
}

.titile_h1 {
  font-weight: bold;
  font-size: 80px;
  line-height: 80px;
  color: white;
}

.corplife {
  font-size: 24px;
  padding-top: 15px;
  font-family: CrocWebLight;
  color: white;
}

.main_title {
  display: flex;
  flex-direction: column;
}

.text {
  font-size: 20px;
  color: #494949;
  font-weight: bold;
}

.main {
  display: flex;
  flex-direction: row;
  justify-content: space-between;
}

.all {
  width: 350px;
}

.link {
  text-decoration: none;
  color: white;
}

.component {
  height: 30px;
}

.count {
  color: #00A460;
  font-size: 42px;
  font-weight: bold;
  text-align: center;
}

.countText {
  font-size: 25px;
  color: #494949;
  font-weight: 300;
  width: 100%;
}

button {
  outline: none;
  cursor: pointer;
  height: 60px;
  width: 100%;
  border: none;
  background-color: #FF645A;
  color: white;
  border-radius: 30px;
  font-weight: bold;
  font-size: 24px;
}

button:hover {
  background-color: #b04740;
}
</style>
