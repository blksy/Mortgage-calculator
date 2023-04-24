<template>
    <div class="mortgage-quote">
         <h1>{{title}}</h1>
         <p>{{ amount }}</p>
    </div>
</template>

<script>
   export default{
    name:'endQuote',
    props:{
        title: String,
        amount: String,
    }
   }
</script>

<style>
    .mortgage-quote{
        font-size: 15px;
    }
</style>