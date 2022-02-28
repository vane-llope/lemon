<template>
<div class="container">
<hr class="mt-5 mb-5" />
    <div class="d-flex JS">
      <div>
         <listofcomp  @comp="callcomp" />
      </div>
    <div class="componentWidth">
      <div class="container">
       <p id="clock" class="text-center mt-2 mb-5" style="font-size:32px"> </p>
         <!--per-->
         <div class="d-flex JS mt-5">
         <p id="perL"></p>
         <p id="perN"></p>
       </div>
       <!--eng-->
       <div class="d-flex JS">
         <p id="engL"></p>
         <p id="engN"></p>
       </div>
       <!--hijri-->
       <div class="d-flex JS">
         <p id="hijriL"></p>
         <p id="hijriN"></p>
       </div>
     </div>
    </div>
    </div>
</div>
</template>
<script>
import listofcomp from './listofcomp.vue';
export default {
    name:'date',
    components: {
    listofcomp,
  },
  methods: {
       callcomp(x){
        this.$emit('comp',x);
      },
  },
  mounted() {
    let myClock = () =>{
      let myDate = new Date();
      //clock
          let clock=document.querySelector("#clock")
          clock.textContent = myDate.getHours() +' : ' +myDate.getMinutes() +' : ' + myDate.getSeconds() 
        } 
      setInterval(myClock,1000);

      const event = new Date();
      const options = { weekday: 'long', year: 'numeric', month: 'long', day: 'numeric' };

      document.querySelector("#perL").textContent=event.toLocaleDateString('per-fa', options)
      document.querySelector("#perN").textContent=event.toLocaleDateString('per-fs')

      document.querySelector("#engL").textContent=event.toLocaleDateString(undefined, options)
      document.querySelector("#engN").textContent=event.toLocaleDateString('en-us')

      
      document.querySelector("#hijriL").textContent=event.toLocaleDateString('ar-sa', options)
      document.querySelector("#hijriN").textContent=event.toLocaleDateString('ar-sa')
  },
}
</script>