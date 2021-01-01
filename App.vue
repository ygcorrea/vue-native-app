<template>
  <view class="container">
    <view>
      <view class="text-container">
        <text class="text-style">Ask and tap</text>
      </view>
      <view class="result-container">
          <touchable-opacity :on-press="getRandomValue">
            <image
              v-if="!clicked"
              :style="{ alignItems: 'center' }"
              :source="require('./assets/moon250.png')"
            />
          </touchable-opacity>
        <view class="xpto">
          <text v-if="clicked">
            <text class="answer-style" v-if="randomNumber == true">Yes</text>
            <text class="answer-style" v-else>No</text>
          </text>
        </view>
        <view>
          <touchable-opacity :on-press="resetValue">
            <image
              v-if="clicked"
              :style="{ alignItems: 'center' }"
              :source="require('./assets/refresh.png')"
            />
          </touchable-opacity>
        </view>
      </view>
    </view>
  </view>
</template>

<script>
export default {
  data() {
    return {
      clicked: false,
      randomNumber: "",
    };
  },
  methods: {
    getRandomValue() {
      this.randomNumber = Math.random() < 0.5;
      this.clicked = true;
    },
    resetValue() {
      this.clicked = false;
    },
  },
};
</script>

<style>
@import url("https://fonts.googleapis.com/css2?family=La+Belle+Aurore&display=swap");
.xpto {
  align-items: center;
  width: 100%;
  margin-bottom: 100px;
}
.container {
  font-family: "La Belle Aurore", cursive;
  flex: 1;
  background-color: #1c0232;
  align-items: center;
  height: 100%;
  /* background-image: url( './assets/bg.png'); */
}
.text-style {
  color: white;
  font-size: 50;

}
.answer-style {
  font-size: 100px;
  color: white;

}

.text-container {
  align-items: center;
  padding-top: 100px;
  height: 250px;
  min-width: 100%;

}
.result-container {
align-items: center;
  padding-top: 100px;
  height: 400px;
  min-width: 100%;
}
.red {
  background-color: red;
}
.green {
  background-color: green;
}
</style>