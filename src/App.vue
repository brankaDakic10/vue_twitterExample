<template>
  <div id="app">
   
    <!-- <Twitterinput /> -->
    <!-- <PasswordInput/> -->


    <!-- example with filter -->
    <article>{{name | allCaps|lowerCase |reverse |currency|join(name,city)}}</article>



    <app-test>
       <!-- 1.example -->
      <!-- <p>This goes into slot</p>
      <div>Slot</div>
      <div>Name: {{name}}</div> -->
        <!-- 2.example -->
      <!-- <p>ASD</p> -->
       <!-- 3.example -->
       <!-- <div slot="header">Header</div>  

      <div slot="footer">Footer</div> -->
      <div slot-scope="slotProps">
        {{slotProps.color}}
        <!-- example with second props must be in the same div -->
        {{slotProps.lastName}}
      </div>
    </app-test>
  </div>
</template>

<script>
// import Twitterinput from './components/Twitterinput.vue'
import PasswordInput from './components/PasswordInput.vue'
import AppTest from './components/AppTest.vue'

export default {
  name: 'app',
  components: {
    // Twitterinput,
    PasswordInput,
    AppTest
  },
   data(){
      return{
           name:"Branka",
           city:"Novi Sad"
      }
  },
  filters:{
    allCaps(value){
      if( !value ){
        return ""
      }
      return value.toString().toUpperCase()
    },
     lowerCase(value){
      if( !value ){
        return ""
      }
      return value.toString().toLowerCase()
    },
    reverse(value){
      if(!value){
        return ""
      }
      return value.split('').reverse().join('')
    },
    currency(value){
      if(!value){
        return ""
      }
      return '$'+value 
    },
    // this value is previous result,arg1 is pased name,arg2 is city
    join(value,arg1,arg2){
      return `${value}+${arg1}+${arg2}`
    }
  }
}
</script>

<style>

</style>
