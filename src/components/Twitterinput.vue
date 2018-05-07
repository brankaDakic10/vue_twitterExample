<template>
  <div>
    <textarea v-model="text" @keydown='handleChange'></textarea>
     <p>{{ numberOfCharacters}}/{{ maxNumberOfCharacters }}</p>
  </div>
</template>

<script>
const MAX_NUMBER_OF_CHARACTERS = 120


export default {
 data(){
   return{
     text:'',
     maxNumberOfCharacters: MAX_NUMBER_OF_CHARACTERS
   }
 },
 methods:{
   handleChange(event){
     
     if(this.numberOfCharacters >= this.maxNumberOfCharacters){
      // this line works with @input on textarea
      //  this.text= this.text.slice(0, this.maxNumberOfCharacters)
       event.preventDefault()
     }
   }
 },
 computed:{
   numberOfCharacters(){
     return this.text.length
   }
 }
 
}
</script>



