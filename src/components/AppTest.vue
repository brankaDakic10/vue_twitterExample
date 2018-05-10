<template>
  <div>

<!-- <slot>
    <p>Some text from the parent here.</p>
    </slot> -->
<!-- <slot name="header"></slot>
<slot name="footer"></slot> -->
<slot :color="color" :lastName="lastName"></slot>
<!-- example with second props  -->

  </div>
</template>
<script>
export default {
 data(){
     return{
         color:"Blue",
         lastName:"Dakic"
     }
 }
}
</script>
