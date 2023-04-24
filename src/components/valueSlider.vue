<template>
    <div class="value-slider">
        <p class="text-area">Title: price USD</p>
        <input ref="input" class="slider" type="range" step="800" min="0" max="9999999" name="" id="">
    </div>
</template>

<script>
  export default{
    name: 'value-slider',
    props:{
        text: String,
        step: String,
        min:String,
        max:String
    },
  }
</script>

<style>

</style>