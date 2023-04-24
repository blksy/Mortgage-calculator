<template>
  <div>
    <div class="app">
      <h1 class="title">Mortgage Calculator</h1>
        <div class="app-container">
          <value-slider></value-slider>
          <value-slider></value-slider>
          <value-slider></value-slider>
          <value-slider></value-slider>
          <end-quote></end-quote>
          <end-quote></end-quote>
          <button class="btn">Get a morgage quote</button>
        </div>
    </div> 
  </div>
</template>

<script>

import valueSlider from './components/valueSlider.vue'
import endQuote from './components/endQuote.vue';

export default{
  name:'App',
  components:{
    valueSlider,
    endQuote,
  }
}

</script>

<style>
* {
  background-color: #7f7f7f;
  color: white;
  font-family: Roboto, Arial, sans-serif;
}

.app-container {
  position: absolute;
  display: grid;
  grid-template-columns: repeat(3, 5fr);
  grid-template-rows: repeat(3, 9vw);
  top: 50%;
  left: 50%;
  transform: translate(-50%, -50%);
  height: 50%;
  width: 70%;
  border: 10px solid white;
  border-radius: 15px;
  padding: 45px;
}

.title{
  font-size:60px;
  margin-left: 670px;
}
.btn{
  width: 400px;
  height: 60px;
  background: #4a006a;
  font-size: 20px;
  border-radius: 15px
}
</style>
