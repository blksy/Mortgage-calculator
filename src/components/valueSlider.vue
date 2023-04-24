<template>
    <div class="value-slider">
        <p class="text-area">{{ text }}: {{this.value}} {{this.unit}}</p>
        <input ref="input" class="slider" type="range" step={{step}} min={{min}} max={{max}} value="0" v-on:change="updateSliderValue($event.target.value)"/>
    </div>
</template>

<script>
  export default{
    name: 'value-slider',
    props:{
        text: String,
        step: String,
        unit: String,
        min:String,
        max:String
    },
    data(){
      return{
        value: this.value || 0
      }
    },
    methods:{
      updateSliderValue(newValue){
        this.value = newValue
        this.$emit('updateSliderValue', newValue)
      }
    },
    mounted(){
      let input = this.$refs.input
      input.step = this.step
      input.min = this.min
      input.max = this.max
    }
  }
</script>

<style>
   .text-area{
    font-size: 25px;
   }
   .slider{
    width: 80%;
    cursor: pointer;
   }

</style>