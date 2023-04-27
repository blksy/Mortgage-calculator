<template>
    <div class="modal-window">
        <h1 class="quote-header">Final Quote</h1>
        <p class="quote-line">Purchase price: {{price}} USD</p>
        <p class="quote-line">Down payment: {{dpayment}} USD</p>
        <p class="quote-line">Repayment period: {{rperiod}} years</p>
        <p class="quote-line">Interest rate: {{irate}} %</p>
        <p class="quote-line">Loan amount: {{loanamount}} USD</p>
        <p class="quote-line">Monthly payment: {{mpayment}} USD</p>
    </div>
</template>

<script>
export default {
  name: 'modal-window',
  props:{
    price:String,
    dpayment:String,
    rperiod:String,
    irate:String,
    loanamount:String,
    mpayment:String
  },
}
</script>

<style>
.modal-window{
    box-shadow: 0 2px 8px rgba(0, 0, 0, 0.33);
    width: 400px;
    height:300px;
    margin-left: 100px;
    background-color: black;
}
.quote-header{
    text-align: center;
    background-color: black;
 
}
.quote-line{
   font-size:  15px;
   text-align: center;
   background-color: black;
}
</style>