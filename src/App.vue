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
          <button>Get a morgage quote</button>
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
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}
</style>
