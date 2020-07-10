<template>
<div class="wrapper">
  <form class="form">
    <p class="title">Помоги своему Санте – заполни небольшую форму о себе</p>
    <label for="about">Немного о себе</label>
    <div class="input_block">
      <input id="about" type="text" v-model="about" required>
      <div class="info" data-title="hello"></div>
    </div>

    <label for="wishlist">Список желаний</label>
    <div class="input_block">
      <input id="wishlist" type="text" v-model="wishlist" required>
    </div>

    <label for="blacklist">То, что совсем не нравится</label>
    <div class="input_block">
      <input id="blacklist" type="text" v-model="blacklist" required>
    </div>
    <button @click='registr'>Готов дарить и получать подарки!</button>
  </form>
</div>
</template>

<script>
export default {
    name: "AboutBlockForm",
    data() {
        return {
            about: '',
            wishlist: '',
            blacklist: '',
        }
    },
          methods: {
              registr() {
                  this.$emit('myEvent', {
                      'about': this.about,
                      'wishlist': this.wishlist,
                      'blacklist': this.blacklist,
                  })
              }
          }
      }
</script>

<style scoped>
.form {
  display: flex;
  flex-direction: column;
  align-items: flex-start;
}

label {
  color: #6B6B6B;
  padding-left: 20px;
  padding-bottom: 10px;
  padding-top: 20px;
  font-size: 20px;
}

input {
  outline: none;
  font-size: 20px;
  padding-left: 10px;
  padding-right: 10px;
  border-radius: 30px;
  border-style: solid;
  border-color: #DDDDDD;
  background-color: #FCFCFC;
  height: 50px;
  width: 550px;
}

.input_block {
  display: flex;
}

.title {
    font-size: 20px;
    color: #ff645a;
}

.info {
  margin-left: 30px;
  margin-top: -10px;
}

button {
  outline: none;
  cursor: pointer;
  height: 60px;
  margin-top: 30px;
  background-color: #FF645A;
  width: 570px;
  border: none;
  color: white;
  border-radius: 30px;
  font-family: CrocWebRegular;
  font-size: 24px;
}

button:hover {
  background-color: #b04740;
}

@media screen and (max-width: 1665px) {
  label {
    padding-left: 20px;
    padding-bottom: 10px;
    padding-top: 20px;
    font-size: 15px;
  }
  input {
    outline: none;
    padding-left: 10px;
    padding-right: 10px;
    font-size: 15px;
    height: 40px;
    width: 500px;
  }
  button {
    height: 50px;
    margin-top: 30px;
    width: 520px;
    font-size: 20px;
  }
  .info {
    margin-left: 30px;
    margin-top: -10px;
  }
}

@media screen and (max-width: 1430px) {
  .title {
    font-size: 16px;
  }
  label {
    padding-left: 20px;
    padding-bottom: 10px;
    padding-top: 15px;
    font-size: 12px;
  }
  input {
    outline: none;
    padding-left: 10px;
    padding-right: 10px;
    font-size: 12px;
    height: 30px;
    width: 400px;
  }
  button {
    height: 40px;
    margin-top: 30px;
    width: 420px;
    font-size: 16px;
  }
}

</style>
