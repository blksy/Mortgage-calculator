<template>
  <div>
    <div class="app">
      <h1 class="title">Mortgage Calculator</h1>
        <div class="app-container">
          <value-slider text="Purchase price" max="1000000" min="0" step="10000" unit="USD" v-on:updateSliderValue="this.purchasePrice = $event"></value-slider>
          <value-slider text="Down payment" max="1000000" min="0" step="10000" unit="USD" v-on:updateSliderValue="this.downPayment = $event"></value-slider>
          <value-slider text="Repayment period" max="45" min="0" step="1" unit="years" v-on:updateSliderValue="this.repaymentTime = $event"></value-slider>
          <value-slider text="Interest rate" max="15" min="0" step="1" unit="%" v-on:updateSliderValue="this.interestRate = $event"></value-slider>
          <!-- <end-quote title="Loan Amount" v-bind:amount=" totalLoanAmount().toString() + ' USD'"></end-quote>
          <end-quote title="Monthly payment" v-bind:amount="calculateMonthlyPayment().toString() + ' USD'"></end-quote>-->
          <button class="btn" @click="openModal = true">Get a morgage quote</button> 
          <modal-window v-show="openModal" 
          :price="this.purchasePrice" 
          :dpayment="this.downPayment" 
          :irate="this.interestRate" 
          :rperiod="this.repaymentTime"
          :loanamount="totalLoanAmount().toString()"
          :mpayment="calculateMonthlyPayment().toString()"
          @click="openModal = false"
          ></modal-window>
        </div>
    </div> 
  </div>
</template>

<script>

import valueSlider from './components/valueSlider.vue'
// import endQuote from './components/endQuote.vue';
import ModalWindow from './components/modalWindow.vue';

export default{
  name:'App',
  components:{
    valueSlider,
    // endQuote,
    ModalWindow,
  },
   data(){
    return{
       openModal:false,
       purchasePrice: 0,
       downPayment:0,
       repaymentTime:0,
       interestRate:0,
       amountBorrowed:0,
       monthlyPayment:0,
    }
  },
  methods:{
    totalLoanAmount(){
      let totalLoan = this.purchasePrice - this.downPayment;
      return totalLoan.toFixed(2);
    },
    calculateMonthlyPayment(){
      let totalLoan = this.purchasePrice - this.downPayment;
      let repaymentTime = this.repaymentTime * 12
      let interestRate = (this.interestRate / 100) /12
      let monthlyPayment = totalLoan * interestRate * (Math.pow(1 + interestRate, repaymentTime)) / (Math.pow(1 + interestRate, repaymentTime) - 1);
      monthlyPayment = monthlyPayment || 0;
      return monthlyPayment.toFixed(2);
    }
  }
}

</script>

<style>
* {
  background-color: #acbdbbbd;
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
  border-radius: 15px;
  margin-top: 200px;
}
</style>
